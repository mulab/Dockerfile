FROM ubuntu:14.04
MAINTAINER mulab.thu@gmail.com
RUN echo "deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y nginx
RUN chown -R www-data:www-data /var/lib/nginx

VOLUME ["/data", "/etc/nginx/sites-enabled", "/var/log/nginx", "/etc/nginx"]

WORKDIR /etc/nginx

CMD ["nginx"]

EXPOSE 80
EXPOSE 442

