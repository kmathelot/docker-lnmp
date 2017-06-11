FROM php:7-fpm-alpine

RUN apk add --no-cache freetype libpng libjpeg-turbo freetype-dev libpng-dev \
  libcurl curl-dev icu-dev libmcrypt-dev libxml2-dev libjpeg-turbo-dev

RUN docker-php-ext-install json mysqli pdo pdo_mysql curl mbstring \
  intl mcrypt xml zip

RUN docker-php-ext-configure gd \
    --with-gd \
    --with-freetype-dir=/usr/include/ \
    --with-png-dir=/usr/include/ \
    --with-jpeg-dir=/usr/include/

RUN docker-php-ext-install gd

RUN apk del --no-cache freetype-dev libpng-dev libjpeg-turbo-dev \
  icu-dev libmcrypt-dev libxml2-dev
