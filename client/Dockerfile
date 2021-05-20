# PRODUCTION DOCKERFILE FOR REACT-APP
# PURPOSE ---> to create a production ready build of our React App and copy that build to Nginx default serving directory.
# We are also going to import our custom "default.conf" file which we have created to override the default configuration of NGINX server.

# MULTI-STAGE DOCKERFILE

FROM node:14.14.0-alpine as builder

WORKDIR '/app'

COPY ./package.json ./

RUN npm install

COPY ./ ./

RUN npm run build

# this will create a folder "build" inside the working directory of your container 

FROM nginx

EXPOSE 3000

# We are exposing a custom port inside the nginx server here, just to remind us later on that this is nginx server with react build
# as react server default port is 3000
# this is not a necessity to expose 3000 only.

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /app/build /usr/share/nginx/html