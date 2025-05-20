FROM debian:latest

LABEL org.opencontainers.image.authors="cfval"

RUN apt-get update && apt-get install -y \
    apache2 \
    && apt-get clean

RUN a2enmod rewrite

EXPOSE 80

CMD ["apache2ctl", "-D", "FOREGROUND"]

