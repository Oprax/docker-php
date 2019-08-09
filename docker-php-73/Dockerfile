FROM oprax/debian:stable

LABEL maintainer="oprax@me.com"

RUN wget -qO - https://packages.sury.org/php/apt.gpg | apt-key add -
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | tee /etc/apt/sources.list.d/php.list
RUN apt-get update
RUN apt-get install -y \
    php7.3-cli \
    php7.3-curl \
    php7.3-xdebug \
    php7.3-mysql \
    php7.3-sqlite \
    php7.3-mbstring \
    php7.3-gd \
    php7.3-xml \
    php7.3-zip \
    php7.3-bcmath \
    php7.3-intl

COPY composer-setup.sh /opt/composer-setup.sh

RUN chmod +x /opt/composer-setup.sh && /opt/composer-setup.sh

