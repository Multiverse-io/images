FROM hexpm/elixir:1.15.6-erlang-26.1.1-debian-bookworm-20230612-slim

ARG DEBIAN_FRONTEND=noninteractive
RUN apt update -y
RUN apt upgrade -y
RUN apt dist-upgrade -y

RUN apt install -y curl bash

RUN apt install -y python3-full

RUN curl -sL https://deb.nodesource.com/setup_16.x | bash -

RUN apt install -y --no-install-recommends python3-pip postgresql-client-15 jq nodejs yarn bc git build-essential imagemagick brotli chromium bash openssh-client docker.io xvfb tar awscli virtualenv

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
