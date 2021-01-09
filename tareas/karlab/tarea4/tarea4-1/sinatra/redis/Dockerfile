# base image
FROM ubuntu:18.04

# author
LABEL maintainer="karlaberlanga15@gmail.com"

# enviroments variables
ENV REFRESHED_AT 2016-06-01

# dependencies
RUN apt-get -yqq update; apt-get -yqq install redis-server redis-tools

# port
EXPOSE 6379

# files
ENTRYPOINT ["/usr/bin/redis-server" ]

CMD []