FROM php:8.3-apache

# Enable Apache modules
RUN a2enmod rewrite proxy_http ssl

# Apache conf
COPY default-ssl.conf /etc/apache2/sites-available/default-ssl.conf
RUN a2ensite default-ssl.conf

# Certbot
RUN apt-get update \
    && apt-get install -y \
        certbot \
        python3-certbot-apache

RUN certbot --apache -d votredomaine.com -m contact@oremis.fr --agree-tos --non-interactive

# Expose port 80
EXPOSE 80

# Start Apache
CMD ["apache2-foreground"]