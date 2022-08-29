FROM php:7.4-apache

RUN curl -sSLf -o /usr/local/bin/install-php-extensions https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions && chmod +x /usr/local/bin/install-php-extensions

RUN install-php-extensions curl zip mysqli xml mbstring gd intl xmlrpc soap opcache memcached redis exif

RUN mkdir /var/www/moodledata && chown www-data:www-data /var/www/moodledata && chmod 755 /var/www/html

WORKDIR /var/www/html/

COPY . .

VOLUME /var/www/html/

VOLUME /var/www/moodledata/

EXPOSE 80