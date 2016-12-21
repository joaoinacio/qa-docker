FROM ubuntu:16.04

COPY apache2-foreground.sh /bin/apache2-foreground

RUN apt-get update
RUN apt-get install -y php-cli \
    apache2 \
    libapache2-mod-php \
    php-readline \
    php-mysqlnd \
    php-json \
    php-xsl \
    php-intl \
    php-mcrypt \
    php-curl \
    php-gd

RUN a2enmod rewrite

CMD "apache2-foreground"
