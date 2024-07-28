FROM php:8.2-fpm

# Install PHP system extensions.
RUN apt update && apt install -y zlib1g-dev g++ libssl-dev libicu-dev libzip-dev zip unzip git \
    && docker-php-ext-install intl opcache mysqli pdo pdo_mysql \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip

# Set working directory
WORKDIR /var/www/html

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN git config --global user.email "balakarthikeyan07@gmail.com" \ 
    && git config --global user.name "Balakarthikeyan"