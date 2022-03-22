FROM php:7.4.23-fpm

RUN apt-get update && apt-get install -y curl git libpng-dev \
    libonig-dev libxml2-dev zip unzip nano

WORKDIR /var/www/html

RUN echo 'memory_limit = -1' >> /usr/local/etc/php/conf.d/docker-php-memlimit.ini;

RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

COPY . /var/www/html/

RUN composer install --no-scripts

RUN chown -R www-data:www-data \
    /var/www/html/public \
    /var/www/html/storage \
    /var/www/html/bootstrap/cache

EXPOSE 9000

CMD ["php-fpm"]
