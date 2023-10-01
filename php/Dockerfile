FROM php:8.2-fpm

ENV TZ Asia/Tokyo

RUN apt-get update && \
    apt-get install -y git unzip libzip-dev libicu-dev libonig-dev mariadb-client vim && \
    docker-php-ext-install intl pdo_mysql zip bcmath

COPY ./php.ini /usr/local/etc/php/php.ini

#Composer install
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

ENV COMPOSER_ALLOW_SUPERUSER 1

ENV COMPOSER_HOME /composer

ENV PATH $PATH:/composer/vendor/bin

WORKDIR /var/www

RUN composer global require "laravel/installer"