FROM php:7.4-apache

# Set the working directory to /var/www/html
WORKDIR /var/www/html

# Copy the four files into the container
COPY *.php style.css ./

RUN chmod 644 ./*php style.css

RUN apt-get update && apt-get install -y

RUN apt-get install git -y

# install Composer in the current directory
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

RUN composer require aws/aws-sdk-php

# Enable Apache mod_rewrite for friendly URLs
RUN a2enmod rewrite

# Expose port 80 for HTTP traffic
EXPOSE 80 443

# Set the default command to start Apache
CMD ["apache2-foreground"]
