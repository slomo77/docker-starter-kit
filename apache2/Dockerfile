FROM php:7.4-apache

RUN a2enmod rewrite
RUN docker-php-ext-install pdo pdo_mysql

RUN mkdir app
COPY . app/

ARG user_id=1000
RUN usermod -u $user_id www-data
RUN chown -R www-data:www-data app
RUN chmod -R 775 app/storage app/bootstrap/cache

COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf
