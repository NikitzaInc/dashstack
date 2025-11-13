# Stage 1 — install dependencies api
FROM php:8.2-fpm-bullseye

RUN apt-get update && apt-get install -y \
    git unzip libpq-dev libpng-dev libjpeg-dev libfreetype6-dev libonig-dev \
    && docker-php-ext-install pdo pdo_mysql mbstring exif pcntl bcmath gd

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www

COPY . .

RUN composer install
RUN chown -R www-data:www-data /var/www/storage /var/www/bootstrap/cache

# Dev-сервер Laravel
CMD ["php", "-S", "0.0.0.0:9000", "-t", "public", "public/index.php"]


