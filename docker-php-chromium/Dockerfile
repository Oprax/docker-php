FROM oprax/php:latest

LABEL maintainer="oprax@me.com" 

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y chromium xvfb
RUN ln -s $(which chromium) /usr/bin/google-chrome
