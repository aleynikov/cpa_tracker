FROM php:7.1-fpm-alpine3.4
RUN apk update --no-cache \
    && apk add --no-cache $PHPIZE_DEPS \
    && apk add --no-cache mysql-dev \
    && docker-php-ext-install mysqli \
    && docker-php-ext-enable mysqli

RUN mkdir -p /var/log/php \
    && chown www-data /var/log/php

ADD php-fpm.conf /usr/local/etc/php-fpm.d/www.conf
