FROM php:7.4-apache
RUN apt update
RUN apt install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libzip-dev libapache2-mod-fcgid
#RUN apt install -y apache2-mpm-prefork

RUN pecl install xdebug-2.9.0

RUN a2enmod rewrite
RUN a2enmod headers

RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install opcache gd pdo_mysql zip
RUN docker-php-ext-enable opcache gd xdebug zip

RUN echo "ServerName localhost" > /etc/apache2/apache2.conf
RUN service apache2 start
