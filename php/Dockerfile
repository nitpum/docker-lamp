FROM php:5.6-apache

RUN docker-php-ext-install mysql mysqli pdo pdo_mysql

RUN docker-php-ext-install pdo_mysql


# Apache conf
# allow .htaccess with RewriteEngine
RUN a2enmod headers
RUN a2enmod rewrite

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

COPY ./apache2/000-default.conf /etc/apache2/sites-available

# autorise .htaccess files
# RUN sed -i '/<Directory \/var\/www\/>/,/<\/Directory>/ s/AllowOverride None/AllowOverride All/' /etc/apache2/apache2.conf

# RUN chgrp -R www-data /var/www
# RUN find /var/www -type d -exec chmod 775 {} +
# RUN find /var/www -type f -exec chmod 664 {} +