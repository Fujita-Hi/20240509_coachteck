FROM php:8.2.12-fpm

COPY php.ini /usr/local/etc/php/

RUN apt update \
    && apt install -y default-mysql-client zlib1g-dev libzip-dev unzip \
    && docker-php-ext-install pdo_mysql zip

RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer \
    && composer self-update

WORKDIR /var/www

RUN apt-get update \
    && apt-get install -y curl \
    && curl -fsSL https://deb.nodesource.com/setup_16.x | bash - \
    && apt-get install -y nodejs