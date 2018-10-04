FROM alpine:3.8

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

# Configure nginx
COPY config/nginx.conf /etc/nginx/nginx.conf

# Configure PHP-FPM
COPY config/fpm-pool.conf /etc/php7/php-fpm.d/zzz_custom.conf
COPY config/php.ini /etc/php7/conf.d/zzz_custom.ini

# Add application
ADD initialServices.sh /
RUN mkdir -p /var/www/html
WORKDIR /var/www/html

EXPOSE 80 443
ENTRYPOINT sh /initialServices.sh
