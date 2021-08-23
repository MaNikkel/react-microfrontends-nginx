# Building app
FROM node:14-alpine as build

WORKDIR /app

COPY . .

RUN npm ci
RUN npm run build

# Starting NGINX
FROM nginx:alpine

COPY nginx/nginx.conf /etc/nginx/nginx.conf

COPY --from=build /app/build /usr/share/nginx/html