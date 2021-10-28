FROM php:7.4.1-fpm

COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

COPY --from=node:14.17 /usr/local/bin /usr/local/bin
COPY --from=node:14.17 /usr/local/lib /usr/local/lib

RUN apt-get update && \
    apt-get -y install \
    git \
    zip \
    unzip \
    vim \
    && docker-php-ext-install pdo_mysql bcmath

WORKDIR /src