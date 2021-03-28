FROM php:8-fpm-alpine as local

ADD ./infrastructure /var/www/html/infrastructure

WORKDIR /var/www/html

RUN apk update && \
    apk add postgresql-dev supervisor gmp-dev gmp &&\
    docker-php-ext-install gmp pcntl pgsql pdo_pgsql bcmath sockets && \
    apk add --no-cache $PHPIZE_DEPS

# INSTALL COMPOSER
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY ./infrastructure/conf/uploads.ini /usr/local/etc/php/conf.d/

CMD php-fpm

FROM local

COPY --chown=www-data:www-data ./ /var/www/html
