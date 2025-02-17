FROM debian:latest

LABEL org.opencontainers.image.authors="cfval_"
LABEL org.opencontainers.image.description="Backend para la gestión de películas"
LABEL org.opencontainers.image.version="1.0"
LABEL org.opencontainers.image.maintainer="cfval_"

RUN apt-get update && apt-get install -y \
    apache2 \
    php \
    php-yaml \
    php-mysql \
    && apt-get clean

RUN a2enmod rewrite && a2enmod headers

EXPOSE 80

CMD ["apache2ctl", "-D", "FOREGROUND"]

