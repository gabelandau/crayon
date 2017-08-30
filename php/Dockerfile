FROM php:7.0-apache

COPY php.ini /usr/local/etc/php/
RUN apt-get update \
  && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng12-dev libmcrypt-dev \
  && docker-php-ext-install pdo_mysql mysqli gd iconv
COPY ./virtualhost.conf  /etc/apache2/sites-available/

RUN service apache2 restart
WORKDIR /etc/apache2/sites-available/
RUN a2ensite virtualhost.conf
