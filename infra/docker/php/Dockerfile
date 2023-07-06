FROM php:8.1-fpm

# composerのインストール
COPY --from=composer:2.2 /usr/bin/composer /usr/bin/composer

RUN apt-get update && \
  apt-get -y install git unzip \
    libzip-dev wget \
    && docker-php-ext-install zip && \
    pecl install xdebug-3.2.1 && \
    docker-php-ext-enable xdebug

COPY php-fpm.d/zzz-www.conf /usr/local/etc/php-fpm.d/zzz-www.conf
COPY php.ini /usr/local/etc/php/php.ini

WORKDIR /work/app
