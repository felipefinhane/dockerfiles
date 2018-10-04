FROM php:7.2.10-fpm-alpine

RUN apk add --update

#PHP EXTENSIONS
RUN echo "---> Installing PHP Extensions" && \
        docker-php-ext-install pdo_mysql

#COMPOSER INSTALL
RUN echo "---> Installing Composer" && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    echo "---> Cleaning up" && \
    rm -rf /tmp/*

#NGINX
RUN echo "---> Installing Nginx" && \
        apk add nginx
