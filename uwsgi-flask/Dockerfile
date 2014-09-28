FROM ubuntu:14.04
MAINTAINER mulab.thu@gmail.com
RUN rm /etc/apt/sources.list
ADD sources.list /etc/apt/sources.list
RUN apt-get update

RUN apt-get install -y \
    build-essential \
    python \
    python-dev \
    python-setuptools
RUN apt-get install -y nginx supervisor
RUN easy_install pip

RUN pip install uwsgi

RUN apt-get install -y python-software-properties

RUN echo "daemon off;" >> /etc/nginx/nginx.conf
ADD . /home/docker/code/

RUN rm /etc/nginx/sites-enabled/default
RUN ln -s /home/docker/code/nginx.conf /etc/nginx/sites-enabled/
RUN ln -s /home/docker/code/supervisord.conf /etc/supervisor/conf.d/

RUN pip install -r /home/docker/code/requirements.txt

VOLUME ["/home/docker/code/app", "/var/log/flask-uwsgi"]

EXPOSE 80
CMD ["supervisord", "-n"]
