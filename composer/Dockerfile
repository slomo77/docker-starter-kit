FROM php:7.4-cli

COPY --from=composer /usr/bin/composer /usr/bin/composer

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    libzip-dev \
    zip \
    unzip

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd zip

RUN useradd -ms /bin/bash newuser
USER newuser

WORKDIR /app

# build image with:
# docker build -t example/tag .

# run following command in folder with composer.json:
# docker run --rm -i --tty -v $(pwd):/app example/tag composer install -d /app