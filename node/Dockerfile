FROM node:18.18.0-alpine

WORKDIR /var/www

RUN apk update && apk upgrade
RUN apk add --no-cache sqlite

ENV LANG=C.UTF-8
ENV TZ=Asia/Tokyo