# Homepage Instructions

Of course, this is an absurdly complicated way of deploying a React SPA.

**Experience is a noun. Perfect is a verb.**

## GKE Setup

### Kubernetes creation

TODO: with `gcloud`

### Istio

Manifest generation to ensure infrastructure as code:

```sh
istioctl manifest generate > istio/manifest.yaml`
```

```sh
k apply -f istio/manifest.yaml
```

### HTTP/S

We use <sslforfree.com> to manage certificates for now.

```sh
k create -n istio-system secret tls istio-ingressgateway-certs \
  --key private.key \
  --cert certificate.crt
```

**Note:** we should use Google managed certificates or even better SDS with Istio (TODO).

## Development

## Deployment

### Locally with skaffold

This is the easiest way to update the homepage:

```sh
skaffold run
```
