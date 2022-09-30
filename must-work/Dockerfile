FROM ubuntu:16.04
MAINTAINER aade <adeawolinux@gmail.com>

RUN apt-get update && \
    apt-get install -y \
    vim \
    curl \
    git \
    apache2 \
    php7.0 \
    libapache2-mod-php7.0 \
    php7.0-mysql \
    php7.0-common \
    php7.0-mysql \
    php7.0-xml \
    php7.0-xmlrpc \
    php7.0-curl \
    php7.0-gd \
    php7.0-cli \
    php7.0-dev \
    php7.0-imap \
    php7.0-mbstring \
    php7.0-opcache \
    php7.0-soap \
    php7.0-zip \
    php7.0-intl && \
    curl -sS https://getcomposer.org/installer -o setup.php && \
    php setup.php --install-dir=/usr/local/bin --filename=composer && \
    rm setup.php
COPY run.sh /usr/local/bin/
COPY mysql-php.php /opt
RUN chmod 700 /usr/local/bin/run.sh 
RUN a2enmod rewrite

EXPOSE 80
ENTRYPOINT ["run.sh"]
