FROM php:7.3.33-apache
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN apt-get update && apt-get install -y zlib1g   zlib1g-dev  libzip-dev
RUN docker-php-ext-install zip
RUN apt-get update && apt-get upgrade -y
WORKDIR /var/www/html
ADD 000-default.conf /etc/apache2/sites-enabled/000-default.conf
RUN a2enmod rewrite  ssl
COPY init.sh  /usr/local/bin/
COPY php.ini //usr/local/etc/php/
ENTRYPOINT [ "bash", "init.sh" ]
