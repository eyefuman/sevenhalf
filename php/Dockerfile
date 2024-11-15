FROM php:8.3-apache

# timezone environment
ENV TZ=Asia/Tokyo \
  # locale
  LANG=ja_JP.UTF-8 \
  LANGUAGE=ja_JP:ja \
  LC_ALL=ja_JP.UTF-8

RUN apt update \
  && apt install -y  \
    git \
    zip \
    unzip \
    vim \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng-dev \
    libfontconfig1 \
    libxrender1 \
    libkrb5-dev libonig-dev \
  && docker-php-ext-install pdo_mysql mysqli mbstring

# Composerをインストール
COPY --from=composer/composer:latest-bin /composer /usr/bin/composer