FROM php:7.1-fpm

# install necessary php modules
RUN docker-php-ext-install mysqli pdo pdo_mysql bcmath

# install required packages and then clean up
RUN apt-get update && apt-get install -y \
        git zip unzip nodejs npm \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer