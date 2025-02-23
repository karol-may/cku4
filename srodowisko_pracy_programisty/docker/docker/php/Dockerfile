FROM php:8.2-fpm
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
WORKDIR /var/www/html
# Instalacja rozszerzenia PDO MySQL
RUN docker-php-ext-install pdo pdo_mysql

EXPOSE 9000
CMD ["php-fpm"]