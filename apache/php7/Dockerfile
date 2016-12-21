FROM ubuntu:16.04

COPY apache2-foreground.sh /bin/apache2-foreground

RUN apt-get update
RUN apt-get install -y php7.0-cli \
    apache2 \
    libapache2-mod-php7.0 \
    php7.0-readline \
    php7.0-mysqlnd \
    php7.0-json \
    php7.0-xsl \
    php7.0-intl \
    php7.0-mcrypt \
    php7.0-curl \
    php7.0-gd

RUN a2enmod rewrite

CMD "apache2-foreground"
