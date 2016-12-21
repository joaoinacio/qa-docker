FROM debian:8

COPY apache2-foreground.sh /bin/apache2-foreground

RUN apt-get update
RUN apt-get install -y php5-cli \
    apache2 \
    libapache2-mod-php5 \
    php5-readline \
    php5-mysqlnd \
    php5-json \
    php5-xsl \
    php5-intl \
    php5-mcrypt \
    php5-curl \
    php5-gd \
    php5-twig \
    php5-memcached

RUN a2enmod rewrite

CMD "apache2-foreground"
