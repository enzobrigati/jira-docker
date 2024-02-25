FROM php:8.3-apache

# Enable Apache modules
RUN a2enmod rewrite proxy_http ssl

# Apache conf
COPY default-ssl.conf /etc/apache2/sites-available/default-ssl.conf
RUN a2dissite 000-default.conf
RUN a2ensite default-ssl.conf