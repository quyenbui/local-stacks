FROM php:7-apache

RUN apt-get update

RUN apt-get install libicu-dev git -y

RUN apt-get install libpng-dev libzip-dev -y

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Copy vhost config
COPY ./apache-vhost.conf /etc/apache2/sites-enabled/apache-vhost.conf

# Enable apache modules
RUN a2enmod rewrite headers

RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install intl
RUN apt-get install libjpeg-dev -y
RUN apt-get install libfreetype6-dev -y
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-install exif
RUN docker-php-ext-install zip
