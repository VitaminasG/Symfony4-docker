FROM php:7.4-fpm

RUN apt-get update && apt-get install -y build-essential && apt-get install -y software-properties-common && apt-get install -y \
    curl \
    wget \
    git \
    nano \
    gnupg \
    man \
    libzip-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng-dev \
    libxml2-dev \
    libxslt1-dev \
    unzip \
    zip \
    cron

RUN docker-php-ext-install mysqli pdo pdo_mysql bcmath xml xsl soap json zip intl
RUN pecl install xdebug-2.8.0
RUN docker-php-ext-enable xdebug

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
COPY ./php/docker-php.ini /usr/local/etc/php/php.ini
