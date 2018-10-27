FROM php:7.1-fpm-alpine3.8

MAINTAINER farshad@nematdoust.com

RUN apk --update add curl \
  grep \
  build-base \
  libmcrypt-dev \
  libxml2-dev \
  zlib-dev \
  autoconf \
  cyrus-sasl-dev \
  libgsasl-dev \
  freetype \
  libpng \
  libjpeg-turbo \
  freetype-dev \
  libpng-dev \
  libjpeg-turbo-dev \
  git \
  mysql-client

RUN	curl -sS https://getcomposer.org/installer | php && \
	mv composer.phar /usr/local/bin/composer && \
	chmod +x /usr/local/bin/composer

RUN docker-php-ext-install mysqli mbstring pdo pdo_mysql tokenizer xml exif

RUN apk add --no-cache --virtual .persistent-deps icu-dev libxml2-dev \
        && docker-php-ext-configure intl --enable-intl \
        && docker-php-ext-configure soap --enable-soap \
        && docker-php-ext-install intl \
        && docker-php-ext-install soap

RUN docker-php-ext-configure gd \
       --with-freetype-dir=/usr/include/ \
       --with-png-dir=/usr/include/ \
       --with-jpeg-dir=/usr/include/ && \
       docker-php-ext-install gd 