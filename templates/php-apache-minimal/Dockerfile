FROM php:7.2-apache

WORKDIR /opt/app

RUN echo 'set -e' > /usr/bin/start.sh # this is the script which will run on start

# Map /opt/app to the default apache home
RUN rm -rf /var/www/html/
RUN ln -s /opt/app /var/www/html

RUN echo '. /etc/apache2/envvars && apache2 -DFOREGROUND' >> /usr/bin/start.sh
