FROM php:8.1-fpm-bullseye

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        gettext-base \
        libz-dev \
        libpq-dev \
        libjpeg-dev \
        libpng-dev \
        libssl-dev \
        libzip-dev \
        unzip \
        zip  \
    && apt-get clean \
    && pecl install redis \
    && docker-php-ext-configure gd \
        --with-jpeg=/usr/include/ \
    && docker-php-ext-configure zip \
    && docker-php-ext-install \
        bcmath \
        gd \
        exif \
        opcache \
        pdo_mysql \
        pdo_pgsql \
        pgsql \
        pcntl \
        zip \
    && docker-php-ext-enable gd \
    && docker-php-ext-enable redis \
    && rm -rf /var/lib/apt/lists/*;

EXPOSE 9000
CMD ["php-fpm"]
