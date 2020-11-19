FROM ubuntu

RUN apt-get update \
 && apt-get install -y \
    apt-utils \
 && apt-get install -y \
    build-essential \
    g++ \
    gcc \
    make \
    liblzma-dev \
    patch \
    ruby \
    ruby-dev \
    zlib1g \
    zlib1g-dev \
 && rm -rf /var/lib/apt/lists/*

RUN gem install jekyll:3.9.0 bundler
