FROM php:7.4-fpm

RUN apt-get update && apt-get install -y libzip-dev libpng-dev zip libicu-dev libxml2-dev libxslt-dev libjpeg-dev libfreetype6-dev sendmail-bin sendmail
RUN docker-php-ext-install bcmath zip intl pdo_mysql soap xsl sockets
RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php-fpm", "-R"]