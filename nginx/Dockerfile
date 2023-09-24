FROM nginx:1.25

ENV TZ=Asia/Tokyo


COPY ./conf.d /etc/nginx/conf.d/

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

WORKDIR /var/www