FROM php:7-fpm

RUN apt update -y
RUN apt upgrade -y
RUN apt install git curl unzip -y
WORKDIR /root
RUN curl -sS https://getcomposer.org/installer -o composer-setup.php
RUN php composer-setup.php --install-dir=/usr/local/bin --filename=composer
COPY ./app/laravel /var/www/html/laravel
RUN chown -R www-data:www-data /var/www/html/laravel/storage
RUN chmod 777 /var/www/html/laravel/storage
WORKDIR /var/www/html/laravel/public
# RUN chmod 777 /var/www/html/laravel/storage/logs
#RUN service php7.1-fpm start
#RUN sysv-rc-conf php7.1-fpm on
# WORKDIR /var/www/html/
# ADD ./app /var/www/html
# RUN composer create-project --prefer-dist laravel/laravel laravel
# WORKDIR /var/www/html/laravel/
# RUN php artisan key:generate
# ADD ./app /var/www/html/laravel
# RUN php artisan serve
