FROM debian:stable

LABEL maintainer="oprax@me.com"

RUN apt-get update
RUN apt-get install -y apt-utils wget gnupg lsb-release apt-transport-https

RUN wget -qO - https://packages.sury.org/php/apt.gpg | apt-key add -
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | tee /etc/apt/sources.list.d/php.list
RUN apt-get update
RUN apt-get install -y \
    php7.1-cli \
    php7.1-xdebug \
    php7.1-mysql \
    php7.1-sqlite \
    php7.1-mbstring \
    php7.1-xml \
    php7.1-zip \
    php7.1-intl

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php -r "if (hash_file('SHA384', 'composer-setup.php') === '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
    php composer-setup.php --install-dir=/usr/local/bin --filename=composer && \
    php -r "unlink('composer-setup.php');"
