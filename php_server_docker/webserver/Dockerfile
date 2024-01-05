FROM php:8.1.1-apache

RUN apt update
RUN apt install -y curl git unzip
RUN curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php
RUN HASH=`curl -sS https://composer.github.io/installer.sig`
RUN php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
RUN php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer
RUN composer --version
RUN rm /tmp/composer-setup.php

#RUN apt update
#RUN apt install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libzip-dev libapache2-mod-fcgid
#RUN apt install -y apache2-mpm-prefork

#RUN pecl install xdebug-2.9.0

#RUN a2enmod rewrite
#RUN a2enmod headers

#RUN docker-php-ext-configure gd --with-freetype --with-jpeg
#RUN docker-php-ext-install opcache gd pdo_mysql zip
#RUN docker-php-ext-enable opcache gd xdebug zip

#RUN echo "ServerName localhost" > /etc/apache2/apache2.conf
RUN service apache2 start
