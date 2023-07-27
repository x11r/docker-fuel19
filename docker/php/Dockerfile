FROM php:7.3-fpm-buster

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

COPY php.ini /usr/local/etc/php/php.ini
COPY xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

RUN apt-get -y update \
    && apt-get -y upgrade \
    && apt-get -y install git unzip vim supervisor tmux \
    && pecl install apcu xdebug-2.9.8 \
    && docker-php-ext-install mysqli pdo_mysql opcache \
    && docker-php-ext-enable apcu xdebug \
