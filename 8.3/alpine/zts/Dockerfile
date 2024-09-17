ARG PHP_VERSION=8.3
FROM php:${PHP_VERSION}-zts-alpine

ARG PHALCON_VERSION=5.8.0
# Base image contains own global PHP_VERSION variable with different value. This is not an accidental duplicate
ARG PHP_VERSION=8.3

USER root
ENV PHPIZE_DEPS="autoconf gcc g++ make"
RUN apk add $PHPIZE_DEPS
RUN ln -s /usr/local/bin/phpize /usr/local/bin/phpize${PHP_VERSION}
RUN pecl -d php_suffix=${PHP_VERSION} install phalcon-${PHALCON_VERSION} >/tmp/phalcon.install.log 2>&1
USER nobody
