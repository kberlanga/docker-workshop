# base image
FROM ubuntu:18.04

# author
LABEL maintainer="karlaberlanga15@gmail.com"

# enviroment variables
ENV REFRESHED_AT 2016-06-01

# dependencies
RUN apt-get update -yqq; apt-get -yqq install ruby ruby-dev build-essential redis-tools
RUN gem install --no-rdoc --no-ri sinatra json redis

# create a folder
RUN mkdir -p /opt/webapp

# port
EXPOSE 4567

# files
CMD [ "/opt/webapp/bin/webapp" ]