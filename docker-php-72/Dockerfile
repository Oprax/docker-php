FROM debian:stable

LABEL maintainer="oprax@me.com"

RUN apt-get update
RUN apt-get install -y apt-utils wget gnupg lsb-release apt-transport-https

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

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php -r "if (hash_file('SHA384', 'composer-setup.php') === '93b54496392c062774670ac18b134c3b3a95e5a5e5c8f1a9f115f203b75bf9a129d5daa8ba6a13e2cc8a1da0806388a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
    php composer-setup.php --install-dir=/usr/local/bin --filename=composer && \
    php -r "unlink('composer-setup.php');"
