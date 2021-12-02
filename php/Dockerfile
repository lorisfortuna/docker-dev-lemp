FROM php:8-fpm-alpine

# install packages
RUN   apk update \
  &&  apk add --no-cache $PHPIZE_DEPS supervisor bash curl unzip git ca-certificates wget \
    zlib-dev libjpeg jpeg-dev libjpeg-turbo libjpeg-turbo-dev libpng libpng-dev \
    libwebp libwebp-dev libzip libzip-dev oniguruma-dev mysql-client msmtp perl \
    procps shadow freetype freetype-dev icu icu-dev \
  &&   update-ca-certificates

# setup php extensions
RUN docker-php-ext-install mysqli \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-configure gd --enable-gd --with-freetype --with-jpeg --with-webp \
    && docker-php-ext-install gd \
    && docker-php-ext-install zip \
    && docker-php-ext-install intl \
    && docker-php-ext-install pcntl \
    && docker-php-ext-install opcache \
    && docker-php-ext-install exif \
    && docker-php-ext-install mbstring

# install composer
RUN wget https://getcomposer.org/composer-stable.phar -O /usr/local/bin/composer && chmod +x /usr/local/bin/composer
