FROM php:8.2.24-fpm

# Install PHP system extensions.
RUN apt update && apt install -y zlib1g-dev g++ libssl-dev libicu-dev libzip-dev zip unzip git \
    && docker-php-ext-install intl opcache mysqli pdo pdo_mysql \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip

# Set working directory
WORKDIR /var/www/html

# COPY php.ini /usr/local/etc/php/php.ini

RUN apt update && apt install -y wget \
    less \
    && rm -rf /var/lib/apt/lists/*

# Install WP CLI
RUN wget https://github.com/wp-cli/wp-cli/releases/download/v2.11.0/wp-cli-2.11.0.phar \
    && chmod +x wp-cli-2.11.0.phar \
    && mv wp-cli-2.11.0.phar /usr/local/bin/wp

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN git config --global user.email "balakarthikeyan07@gmail.com" \ 
    && git config --global user.name "Balakarthikeyan"