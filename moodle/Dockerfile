FROM php:8.3.24-apache

RUN apt-get update && apt-get install -y \
    libpq-dev \
    libzip-dev \
    libicu-dev \
    libxml2-dev \
    libjpeg-dev \
    libpng-dev \
    libfreetype6-dev \
    libsodium-dev \
    libonig-dev \
    libcurl4-openssl-dev \
    unzip curl git \
&&  docker-php-ext-configure gd --with-freetype --with-jpeg \
&&  docker-php-ext-install -j"$(nproc)" \
    pgsql pdo_pgsql intl zip soap gd opcache mbstring sodium \
    curl xml \
&&  rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite
WORKDIR /var/www/html
