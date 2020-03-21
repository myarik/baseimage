FROM python:2.7-slim-buster

LABEL maintainer="Yaroslav Muravskyi <y@myarik.com>"

ENV PYTHONUNBUFFERED 1

RUN apt-get update \
  # dependencies for building Python packages
  && apt-get install -y build-essential \
  # psycopg2 dependencies
  && apt-get install -y libpq-dev \
  # Translations dependencies
  && apt-get install -y gettext \
  # Extra packages
  && apt-get -y install curl \
          libssl-dev \
          g++ \
          git-core \
          libbz2-dev \
          libcairo2-dev \
          libevent-dev \
          libffi-dev \
          libfreetype6 \
          libfreetype6-dev \
          libgraphviz-dev \
          libjpeg62-turbo-dev \
          libjpeg-dev \
          libxml2-dev \
          libxslt1-dev \
          libxslt-dev \
          pkg-config \
          libncurses5-dev \
          libncursesw5-dev \
          tzdata \
  # cleaning up unused files
  && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false \
  && rm -rf /var/lib/apt/lists/*

RUN cp /usr/share/zoneinfo/America/New_York /etc/localtime