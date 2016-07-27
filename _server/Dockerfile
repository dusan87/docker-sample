FROM python:2.7
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN apt-get update && apt-get install -y \
        build-essential \
        nginx \
        supervisor \
    && rm -rf /var/lib/apt/lists/*

RUN pip install uwsgi

# setup all the configfiles
RUN echo "daemon off;" >> /etc/nginx/nginx.conf
COPY config/nginx.conf /etc/nginx/sites-available/default
COPY config/supervisor.conf /etc/supervisor/conf.d/

COPY . ${ENV_SERVER_HOME}/

EXPOSE 80
CMD ["supervisord", "-n"]
