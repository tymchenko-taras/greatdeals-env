FROM php:7.2-fpm

RUN apt-get update && apt-get install -y \
    libmcrypt-dev \
    mysql-client \
    libmemcached-dev \
    libzip-dev \
    zip\
    libxml2 libxml2-dev\
    libpng-dev\
    && docker-php-ext-configure zip --with-libzip\
    && docker-php-ext-install gd zip pdo_mysql mbstring xml\
    && apt-get clean all

RUN pecl install mcrypt-1.0.1 \
    && pecl install xdebug-2.6.0 \
    && pecl install memcached-3.0.0 \
    && pecl install mongodb\
    && docker-php-ext-enable mcrypt xdebug memcached mongodb\
    && apt-get clean all

EXPOSE 9000
