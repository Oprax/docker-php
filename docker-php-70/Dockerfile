FROM oprax/debian:stable

LABEL maintainer="oprax@me.com"

RUN wget -qO - https://packages.sury.org/php/apt.gpg | apt-key add -
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | tee /etc/apt/sources.list.d/php.list
RUN apt-get update
RUN apt-get install -y \
    php7.0-cli \
    php7.0-curl \
    php7.0-xdebug \
    php7.0-mysql \
    php7.0-sqlite \
    php7.0-mbstring \
    php7.0-gd \
    php7.0-xml \
    php7.0-zip \
    php7.0-intl

COPY composer-setup.sh /opt/composer-setup.sh

RUN chmod +x /opt/composer-setup.sh && /opt/composer-setup.sh
