FROM alpine:3.8
#FROM php:7.2.9-fpm-alpine
LABEL Maintainer="Felipe Finhane de Paula <felipe@finhane.com>" \
      Description="Nginx & PHP-FPM based on Alpine Linux."

# Install packages and php extensions
RUN apk --no-cache add \
        php7 \
        php7-fpm \
        php7-session \
        php7-pdo \
        php7-json \
        php7-phar \
        php7-xml \
        php7-fileinfo \
        php7-openssl \
        php7-curl \
        php7-tokenizer \
        php7-iconv \
        php7-ctype \
        nginx \
        curl 
#NFEPHP
#        php7-mbstring \
#        php7-dom \
#        php7-soap \
#        php7-simplexml \
#        php7-gd \
#        php7-mcrypt \ 
#        php7-zip \ 
#        php7-common

# Configure nginx
COPY config/nginx.conf /etc/nginx/nginx.conf

# Configure PHP-FPM
COPY config/fpm-pool.conf /etc/php7/php-fpm.d/zzz_custom.conf
COPY config/php.ini /etc/php7/conf.d/zzz_custom.ini

#COMPOSER INSTALL
#RUN echo "---> Installing Composer" && \
#        curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
#        echo "---> Cleaning up" && \
#        rm -rf /tmp/*
#
# Add application
ADD teste.sh /
RUN mkdir -p /var/www/html
WORKDIR /var/www/html

EXPOSE 80 443
ENTRYPOINT sh /teste.sh
