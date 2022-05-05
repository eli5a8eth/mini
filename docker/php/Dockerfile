FROM php:7.4-fpm

RUN apt update --fix-missing \
    && apt install -y zlib1g-dev g++ git libicu-dev zip libzip-dev zip \
    && apt -y install -qq --force-yes mc cron \
    && apt install -y nodejs \
    && docker-php-ext-install intl opcache pdo_mysql mysqli zip\
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && curl -sL https://deb.nodesource.com/setup_18.x | bash - \
    && curl -sS https://get.symfony.com/cli/installer | bash \
    && mv /root/.symfony/bin/symfony /usr/local/bin/symfony

WORKDIR /var/www