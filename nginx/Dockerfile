FROM mulab/ubuntu:14.04
MAINTAINER mulab.thu@gmail.com
RUN add-apt-repository -y ppa:nginx/stable
RUN apt-get update
RUN apt-get install -y nginx
RUN rm -rf /var/lib/apt/lists/*
RUN echo "\ndaemon off;" >> /etc/nginx/nginx.conf
RUN chown -R www-data:www-data /var/lib/nginx

VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/var/log/nginx", "/etc/nginx/conf.d", "/data"]

WORKDIR /etc/nginx

CMD ["nginx"]

EXPOSE 80
EXPOSE 442

