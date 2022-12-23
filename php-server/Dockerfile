FROM php:8.2.0-fpm

RUN apt-get update && apt-get install -y \
        curl \
        wget \
        git \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
	libpng-dev \
	libonig-dev \
	libicu-dev \
	zlib1g-dev libicu-dev g++ \
	&& docker-php-ext-configure gd --with-freetype --with-jpeg \
	&& docker-php-ext-configure intl \
        && docker-php-ext-configure gettext \
    	&& docker-php-ext-configure opcache --enable-opcache \
    	&& docker-php-ext-configure pcntl --enable-pcntl \
    	# && docker-php-ext-configure soap \
    	&& docker-php-ext-install gettext \
    	&& docker-php-ext-install pcntl \
        && docker-php-ext-install iconv \
        && docker-php-ext-install mbstring \
        && docker-php-ext-install mysqli \
        && docker-php-ext-install pdo_mysql \

        && docker-php-ext-install -j$(nproc) gd \
    	&& docker-php-ext-configure intl \
    	&& docker-php-ext-install intl




# composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
RUN /usr/local/bin/composer self-update

# Добавим свой php.ini, можем в нем определять свои значения конфига
#ADD php.ini /usr/local/etc/php/conf.d/40-custom.ini

# рабочая директория PHP
WORKDIR /var/www