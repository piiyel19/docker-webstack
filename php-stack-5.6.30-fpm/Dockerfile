FROM php:5.6.30-fpm
RUN apt-get update && apt-get upgrade -y \
    libssl-dev \
    libssl-doc \
    libsasl2-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpq-dev \
    libmagickwand-dev \
    libmcrypt-dev \
    libpng12-dev \
    libmemcached-dev \
    zlib1g-dev \
    && docker-php-ext-install -j$(nproc) bz2 iconv mcrypt mbstring pdo_mysql mysql mysqli pgsql pdo_pgsql zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

# Install xdebug
# RUN pecl install xdebug && docker-php-ext-enable xdebug

# Install MongoDB Client
# RUN pecl install mongodb && docker-php-ext-enable mongodb

# Install Redis Client
# RUN pecl install redis && docker-php-ext-enable redis