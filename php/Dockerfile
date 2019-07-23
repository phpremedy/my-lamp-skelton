ARG PHP_VERSION=""
FROM php:${PHP_VERSION:+${PHP_VERSION}-}fpm
RUN apt-get update && apt-get install -y \
		libxslt-dev \
		libfreetype6-dev \
		libjpeg62-turbo-dev \
		libcurl3-dev \
		libmcrypt-dev \
		libpng-dev \
		libtidy-dev \
		curl \
	&& docker-php-ext-install -j$(nproc) iconv mcrypt \
	&& docker-php-ext-install -j$(nproc) mysqli zip pdo curl pdo_mysql xsl xml soap simplexml session tidy bcmath \
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) gd
