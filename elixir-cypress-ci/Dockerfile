FROM hexpm/elixir:1.13.4-erlang-25.0.2-debian-bullseye-20210902-slim

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get dist-upgrade -y

RUN apt-get install -y curl bash

RUN curl -sL https://deb.nodesource.com/setup_16.x | bash -

RUN apt-get install -y \
    bc \
    brotli \
    git \
    imagemagick \
    jq \
    libasound2 \
    libgbm-dev \
    libgconf-2-4 \
    libgtk-3-0 \
    libgtk2.0-0 \
    libnotify-dev \
    libnss3 \
    libxss1 \
    libxtst6 \
    nodejs \
    openssh-client \
    postgresql-client \
    python3-pip \
    wkhtmltopdf \
    xauth \
    xvfb \
    chromium

RUN npm install --global yarn

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
