ARG VARIANT=8-bookworm
FROM mcr.microsoft.com/vscode/devcontainers/php:1-${VARIANT}

# Install packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
  && apt-get install -y --no-install-recommends \
    libfreetype6-dev \
    libjpeg-dev \
    libpng-dev \
    libwebp-dev \
  && apt-get clean -y \
  && rm -rf /var/lib/apt/lists/*

# Dsiable xdebug by default.
ARG XDEBUG_MODE="off"
ENV XDEBUG_MODE=$XDEBUG_MODE

# Install php extensions for Drupal.
RUN docker-php-ext-configure gd \
  --with-freetype \
  --with-jpeg=/usr \
  --with-webp \
  && docker-php-ext-install -j$(nproc) gd pdo_mysql opcache

# Set general recommended settings for opcache.
# see https://secure.php.net/manual/en/opcache.installation.php
RUN { \
    echo 'opcache.memory_consumption=128'; \
    echo 'opcache.interned_strings_buffer=8'; \
    echo 'opcache.max_accelerated_files=4000'; \
    echo 'opcache.revalidate_freq=60'; \
    echo 'opcache.fast_shutdown=1 ; prior to PHP 7.2.0'; \
    echo 'opcache.enable_cli=1'; \
  } > /usr/local/etc/php/conf.d/opcache-recommended.ini


# Change document root for Apache
# see: https://github.com/docker-library/php/issues/246
ARG APACHE_DOCUMENT_ROOT="/workspace/drupalcms-codespaces-sandbox/web/"
ENV APACHE_DOCUMENT_ROOT=$APACHE_DOCUMENT_ROOT
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
RUN a2enmod expires rewrite

# [Choice] Node.js version: none, lts/*, 16, 14, 12, 10
ARG NODE_VERSION="none"
RUN if [ "${NODE_VERSION}" != "none" ]; then su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi
