FROM mulab/nginx
MAINTAINER mulab.thu@gmail.com

RUN apt-get update
RUN apt-get install -y \
    python \
    python-dev \
    python-setuptools \
    python-software-properties \
    supervisor

RUN easy_install pip
RUN pip install uwsgi flask

COPY nginx.conf /etc/nginx/sites-enabled/default
COPY uwsgi_param /conf/uwsgi_param
COPY uwsgi.ini /conf/uwsgi.ini
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

VOLUME ["/var/log/uwsgi-flask", "/conf", "/data"]

EXPOSE 80
CMD ["supervisord", "-n"]
