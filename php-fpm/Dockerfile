FROM php:7.1-fpm-alpine

# install necessary php modules
RUN docker-php-ext-install mysqli pdo_mysql bcmath

# install required packages, git and node+npm
RUN apk --no-cache add \
    git zip unzip nodejs

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# match container user to volume host's user
RUN sed -ri 's/^www-data:x:82:82:/www-data:x:1000:50:/' /etc/passwd