### Stage 1: build

FROM node:18.14-alpine as node
ARG configuration=production

WORKDIR /angular
COPY app/package.json app/package-lock.json /angular/app/

# Install app dependencies
RUN npm install --prefix app

# Copy app files
COPY . /angular
# Build app
RUN npm run build --prefix app -- --output-path=./dist/out --configuration $configuration


### Stage 2: delivery

FROM nginx:1.23.3-alpine

# Remove default nginx website
RUN rm -rf /usr/share/nginx/html/*
# Copy app to nginx image
COPY --from=node /angular/app/dist/out /usr/share/nginx/html
# Copy nginx configuration file
COPY ./nginx/nginx.conf /etc/nginx/conf.d/default.conf