FROM php:7.2-apache

RUN apt-get update && apt-get install -y libmcrypt-dev \
        && pecl install mcrypt-1.0.2 \
        && docker-php-ext-enable mcrypt \
    g++ git libicu-dev zip \
    libzip-dev \
    zip \
    && docker-php-ext-install intl opcache pdo_mysql \
    && pecl install apcu xdebug-2.7.0RC2 redis\
    && docker-php-ext-enable apcu xdebug redis\
    && docker-php-ext-configure int zip --with-libzip \
    && docker-php-ext-install intl zip \

WORKDIR /usr/src/app

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY . /app








