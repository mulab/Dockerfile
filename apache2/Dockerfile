FROM ubuntu:14.04

MAINTAINER mulab.thu@gmail.com
RUN echo "deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y openssh-server apache2 supervisor
RUN mkdir -p /var/run/sshd
RUN mkdir -p /var/log/supervisor

ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf

VOLUME ["/var/www"]

EXPOSE 22 80
CMD ["/usr/bin/supervisord"]
