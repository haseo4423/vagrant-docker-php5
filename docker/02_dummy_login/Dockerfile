FROM php:5.6-apache

RUN apt-get update \
  && apt-get install -y \
  curl \
  build-essential \
  openssl libssl-dev \
  libcurl4-openssl-dev \
  libmcrypt-dev \
  libpq-dev \
  libxml2-dev \
  libldap2-dev \
  libgd-dev \
  libfreetype6-dev \
  libjpeg62-turbo-dev \
  libpng-dev \
  zlib1g-dev \
  zip \
  unzip \
  && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
  && docker-php-ext-install -j$(nproc) mcrypt curl iconv tokenizer mbstring pdo pdo_pgsql xmlrpc \
  && a2enmod rewrite \
  && a2enmod ssl \
  && a2dissite 000-default
