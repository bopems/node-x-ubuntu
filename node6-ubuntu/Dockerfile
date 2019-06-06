FROM ubuntu:latest

MAINTAINER Bope Microservices - bopems/node:6-ubuntu

RUN apt-get update
RUN apt-get -y install apt-transport-https \
      ca-certificates \
      gnupg2 \
      curl \
      software-properties-common

RUN apt-get -y install \
      nano \
      python && \
    apt-get update

RUN cd ~
RUN curl -sL https://deb.nodesource.com/setup_6.x -o nodesource_setup.sh
RUN bash nodesource_setup.sh && apt-get update
RUN apt-get -y install nodejs
RUN apt-get install -y build-essential
RUN apt-get install -y npm

COPY docker-entrypoint.sh /usr/local/bin/
ENTRYPOINT ["docker-entrypoint.sh"]

CMD ["node"]
