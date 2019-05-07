FROM python:2.7-alpine

LABEL maintainer="Yaroslav Muravskyi <y@myarik.com>"

ENV PYTHONUNBUFFERED 1

RUN apk update \
    # psycopg2 dependencies
    && apk add --virtual build-deps gcc python-dev musl-dev linux-headers make curl\
    && apk add postgresql-dev \
    # Pillow dependencies
    && apk add jpeg-dev zlib-dev freetype-dev lcms2-dev openjpeg-dev tiff-dev tk-dev tcl-dev \
    # CFFI dependencies
    && apk add libffi-dev py-cffi libressl-dev libxml2-dev libxslt-dev\
    # Translations dependencies
    && apk add gettext \
    # https://docs.djangoproject.com/en/dev/ref/django-admin/#dbshell
    && apk add postgresql-client

RUN \
    apk add --no-cache --update tzdata git bash curl && \
    cp /usr/share/zoneinfo/America/New_York /etc/localtime && \
    rm -rf /var/cache/apk/*