FROM ubuntu

# System requirements locale settings


RUN apt-get update && apt-get install -y \
  locales \
  build-essential \
  curl \
  python3-pip \
  swig \
  && rm -rf /var/lib/apt/lists/* && locale-gen "en_US.UTF-8"

ENV LANG=en_US.UTF-8 \
    LANGUAGE=en_US:en \
    LC_ALL=en_US.UTF-8

# Upgrade pip then install dependencies
RUN pip3 install --upgrade pip
RUN curl https://raw.githubusercontent.com/automl/auto-sklearn/master/requirements.txt \
  | xargs -n 1 -L 1 pip3 install

# Install
RUN pip3 install \
  auto-sklearn \
  jupyter
