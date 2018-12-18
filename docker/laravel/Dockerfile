FROM composer:1.8 AS composer
FROM php:7.2-cli

# Install composer
COPY --from=composer /usr/bin/composer /usr/bin/composer

ENV COMPOSER_ALLOW_SUPERUSER 1

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      # for composer
      unzip=6.0-21 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app

# Install dependency library
COPY composer.json .
COPY composer.lock .
RUN composer install --no-autoloader --no-scripts --no-suggest --ignore-platform-reqs

COPY . .

# Run dump-autoload and scripts
RUN composer install

CMD ["php", "-S", "0.0.0.0:80", "public/index.php"]
