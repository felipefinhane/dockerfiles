FROM composer:latest

RUN apk update; \
    apk upgrade; \
    apk add --no-cache --virtual libxslt-dev; \
    docker-php-ext-install xsl

RUN apk add --update --no-cache libintl icu icu-dev libxml2-dev \
    && docker-php-ext-install intl zip
