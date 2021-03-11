FROM php:7.3-apache-buster

RUN apt update && apt install -y wget && wget https://github.com/glpi-project/glpi/releases/download/9.5.3/glpi-9.5.3.tgz -O /tmp/glpi.tgz  \
&& tar -zxvf /tmp/glpi.tgz -C /var/www/html/ \
&& chmod -R 777 /var/www/html/ \ 

&& apt install -y libicu-dev libpng-dev libldap2-dev libpcre3-dev libxml2-dev libbz2-dev libzip-dev  && pecl install APCu  \

&& docker-php-ext-install intl mysqli opcache bz2 xmlrpc exif gd zip ldap \

&& docker-php-ext-enable apcu \

&& wget https://github.com/fusioninventory/fusioninventory-for-glpi/releases/download/glpi9.5%2B2.0/fusioninventory-9.5+2.0.tar.bz2 \
&& tar -xvjf fusioninventory-*.tar.bz2 -C /var/www/html/glpi/plugins/ \

&& apache2ctl restart
