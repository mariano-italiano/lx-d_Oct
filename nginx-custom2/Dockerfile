FROM alpine AS helper

RUN apk add git
WORKDIR /src
ARG NGINX_CONTENT_BRANCH=1.0
RUN git clone https://github.com/mariano-italiano/docker.git && cd docker/html && git checkout $NGINX_CONTENT_BRANCH 

FROM nginx:1.19.2
MAINTAINER Marcin Kujawski v1.0
RUN apt-get update && apt-get install -y nginx && apt-get clean && rm -rf /var/lib/apt/lists/*
COPY --from=helper /src/docker/html/index.html /usr/share/nginx/html/index.html


