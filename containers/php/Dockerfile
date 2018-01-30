FROM php:7.2-fpm-alpine

# phpize
RUN apk add --update --no-cache $PHPIZE_DEPS

# ftp
RUN apk add --update --no-cache openssl-dev \
    && docker-php-ext-install ftp

# gd
RUN apk add --update --no-cache libjpeg-turbo-dev libpng-dev libwebp-dev \
    && docker-php-ext-install gd

# iconv
RUN docker-php-ext-install iconv

# intl
RUN apk add --update --no-cache icu-dev \
    && docker-php-ext-install intl

# json
RUN docker-php-ext-install json

# mcrypt
RUN apk add --update --no-cache libmcrypt-dev \
    && yes '' | pecl install mcrypt-snapshot \
    && docker-php-ext-enable mcrypt

# mbstring
RUN docker-php-ext-install mbstring

# mysqli
RUN docker-php-ext-install mysqli

# opcache
RUN docker-php-ext-enable opcache

# zip
RUN apk add --update --no-cache libzip-dev \
    && docker-php-ext-install zip

# apcu
RUN yes '' | pecl install apcu \
    && docker-php-ext-enable apcu
