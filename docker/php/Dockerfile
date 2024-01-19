# ./docker/php/Dockerfile

FROM composer:2.6.6 as composer

FROM php:8.3-fpm-alpine3.19
RUN apk add --no-cache \
    bash=~5.2 \
    git=~2.43 \
    icu-dev=~74.1 \
    make

RUN mkdir -p /var/www/app \
    && apk add --no-cache --virtual=.build-deps \
        autoconf=~2.71 \
        g++=~13.2 \
    && docker-php-ext-configure intl \
    && docker-php-ext-install -j"$(nproc)" intl pdo_mysql \
    && pecl install apcu \
    && docker-php-ext-enable apcu intl \
    && pecl install redis  \
    && docker-php-ext-enable redis \
    && apk del .build-deps

WORKDIR /var/www/app/
COPY app .

RUN PATH=$PATH:/var/www/app/vendor/bin:bin
COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN chown -R 1000:1000 /var/www/app
USER 1000:1000

CMD bash -c 'composer install --no-scripts --ignore-platform-reqs && php-fpm'