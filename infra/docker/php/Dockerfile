FROM php:8.2-fpm

# composerのインストール
COPY --from=composer:2.2 /usr/bin/composer /usr/bin/composer

RUN apt-get update && \
  apt-get -y install git unzip \
    libzip-dev \
    && docker-php-ext-install zip

WORKDIR /work/app
