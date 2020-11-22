FROM registry.oprax.fr/debian:stable

LABEL maintainer="oprax@me.com"

RUN wget -qO - https://packages.sury.org/php/apt.gpg | apt-key add -
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | tee /etc/apt/sources.list.d/php.list
RUN apt update
RUN apt install -y \
    php7.4-cli \
    php7.4-curl \
    php7.4-xdebug \
    php7.4-mysql \
    php7.4-sqlite \
    php7.4-mbstring \
    php7.4-imagick \
    php7.4-gd \
    php7.4-xml \
    php7.4-zip \
    php7.4-bcmath \
    php7.4-intl

COPY composer-setup.sh /opt/composer-setup.sh

RUN chmod +x /opt/composer-setup.sh && /opt/composer-setup.sh

