# build environment
FROM node:alpine as build
WORKDIR /app

COPY package.json /app/package.json
RUN npm install --silent
COPY . /app
RUN npm run build

# production environment
FROM nginx:1.17.3-alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]