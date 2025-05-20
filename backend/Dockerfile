FROM debian:latest

LABEL org.opencontainers.image.authors="cfval"

RUN apt-get update && apt-get install -y \
    apache2 \
    php \
    php-yaml \
    php-mysql \
    && apt-get clean

RUN a2enmod rewrite && a2enmod headers

EXPOSE 80

CMD ["apache2ctl", "-D", "FOREGROUND"]

