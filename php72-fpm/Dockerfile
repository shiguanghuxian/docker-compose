FROM php:7.2.17-fpm-alpine3.8

LABEL maintainer="shiguanghuxian <shiguanghuxian@live.com>"

RUN cd /etc/apk \
    && sed 's/http:\/\/dl-cdn.alpinelinux.org/https:\/\/mirrors.aliyun.com/g' -i /etc/apk/repositories

# 安装依赖
RUN apk update \
    # && apk upgrade \
    && apk add --no-cache \
        curl \
        tzdata \
        php7-fpm \
        php7 \
        php7-dev \
        php7-apcu \
        php7-bcmath \
        php7-xmlwriter \
        php7-ctype \
        php7-curl \
        php7-exif \
        php7-iconv \
        php7-intl \
        php7-json \
        php7-mbstring \
        php7-opcache \
        php7-openssl \
        php7-pcntl \
        php7-pdo \
        php7-mysqlnd \
        php7-mysqli \
        php7-pdo_mysql \
        php7-pdo_pgsql \
        php7-phar \
        php7-posix \
        php7-session \
        php7-xml \
        php7-simplexml \
        php7-mcrypt \
        php7-xsl \
        php7-zip \
        php7-zlib \
        php7-dom \
        php7-redis \
        php7-tokenizer \
        php7-gd \
        php7-mongodb\
        php7-fileinfo \
        php7-zmq \
        php7-memcached \
        php7-xmlreader \
        && rm -rf /var/cache/apk/*

RUN docker-php-ext-install mysqli pdo_mysql

RUN apk add --no-cache gcc g++ zlib zlib-dev make re2c curl bash file rabbitmq-c-dev

# 安装grpc扩展和mq扩展和redis
RUN pecl install grpc \
    && pecl install protobuf \
    && pecl install amqp \
    && pecl install redis \
    && echo "extension=grpc.so" > /usr/local/etc/php/conf.d/grpc.ini \
    && echo "extension=protobuf.so" > /usr/local/etc/php/conf.d/protobuf.ini \
    && echo "extension=amqp.so" > /usr/local/etc/php/conf.d/amqp.ini \
    && echo "extension=redis.so" > /usr/local/etc/php/conf.d/redis.ini

# 安装phalconphp
ENV PHALCON_VERSION=3.4.2

RUN set -xe && \
    curl -LO https://github.com/phalcon/cphalcon/archive/v${PHALCON_VERSION}.tar.gz && \
    tar xzf v${PHALCON_VERSION}.tar.gz && cd cphalcon-${PHALCON_VERSION}/build && ./install && \
    echo "extension=phalcon.so" > /usr/local/etc/php/conf.d/phalcon.ini && \
    cd ../.. && rm -rf v${PHALCON_VERSION}.tar.gz cphalcon-${PHALCON_VERSION} \
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/* \
    && rm -rf /usr/src/php


EXPOSE 9000
