FROM ubuntu:14.04
MAINTAINER mulab.thu@gmail.com
RUN echo "deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y nginx
RUN chown -R www-data:www-data /var/lib/nginx
RUN echo "\ndaemon off;" >> /etc/nginx/nginx.conf

VOLUME ["/data", "/var/log/nginx", "/etc/nginx/sites-enabled"]

WORKDIR /etc/nginx

CMD ["nginx"]

EXPOSE 80
EXPOSE 442

