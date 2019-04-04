#Redis is not authorized to access

# Base image to use, this nust be set as the first line
FROM ubuntu:16.04

# Maintainer: docker_user <docker_user at email.com> (@docker_user)
MAINTAINER ju5ton1y

RUN echo "deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse" > /etc/apt/sources.list

RUN apt-get update
RUN apt-get install -y openssh-server make gcc
#RUN wget http://download.redis.io/releases/redis-3.2.11.tar.gz
COPY redis-3.2.11.tar.gz ./
RUN tar xzf redis-3.2.11.tar.gz
RUN cd redis-3.2.11 && make && cd src && cp redis-server /usr/bin &&  cp redis-cli /usr/bin
ADD redis.conf /etc/redis.conf
ADD sshd_config /etc/ssh/sshd_config

EXPOSE 6379 22

RUN /etc/init.d/ssh restart
CMD ["redis-server", "/etc/redis.conf"]

