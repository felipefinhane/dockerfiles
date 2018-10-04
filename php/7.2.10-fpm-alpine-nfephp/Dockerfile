FROM php:7.2.10-fpm-alpine

RUN apk add --update

RUN apk add --no-cache \
        curl-dev \
        libxml2-dev \
        libpng-dev \
        libmcrypt-dev

RUN apk add --no-cache php7-mcrypt

RUN docker-php-ext-install curl \
        dom \
        json \
        gd \
        mbstring \
        #openssl \
        soap \
        xml \
        zip
        #mcrypt

#COMPOSER INSTALL
RUN echo "---> Installing Composer" && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    echo "---> Cleaning up" && \
    rm -rf /tmp/*

#APPLICATION DIRECTOR
WORKDIR "/workspace"

# Environment variables
ENV PATH=/home/ambientum/.composer/vendor/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

# As non daemon and single base image, it may be used as cli container
CMD ["/bin/bash"]