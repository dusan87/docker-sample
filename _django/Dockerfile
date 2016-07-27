FROM python:2.7
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

MAINTAINER Revelsystems

RUN virtualenv ${ENV_APP_VIRTUALENV_PATH}

COPY requirements /tmp/requirements
RUN source ${ENV_APP_VIRTUALENV_PATH}/bin/activate && pip install -r /tmp/requirements/base.txt

COPY . ${ENV_APP_HOME}/

VOLUME ${ENV_APP_HOME}/
VOLUME ${ENV_APP_VIRTUALENV_PATH}/