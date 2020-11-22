FROM registry.oprax.fr/php:7

LABEL maintainer="oprax@me.com" 

RUN apt update && apt upgrade -y
RUN apt install -y chromium xvfb
RUN ln -s $(which chromium) /usr/bin/google-chrome
