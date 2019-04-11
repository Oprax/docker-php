FROM oprax/debian:stable

LABEL maintainer="oprax@me.com"

RUN wget -qO - https://packages.sury.org/php/apt.gpg | apt-key add -
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | tee /etc/apt/sources.list.d/php.list
RUN apt-get update
RUN apt-get install -y \
    php7.2-cli \
    php7.2-curl \
    php7.2-xdebug \
    php7.2-mysql \
    php7.2-sqlite \
    php7.2-mbstring \
    php7.2-gd \
    php7.2-xml \
    php7.2-zip \
    php7.2-intl

COPY composer-setup.sh /opt/composer-setup.sh

RUN chmod +x /opt/composer-setup.sh && /opt/composer-setup.sh

