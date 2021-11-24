FROM hexpm/elixir:1.12.3-erlang-24.1.2-bullseye-20210902-slim

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get dist-upgrade -y
RUN apt-get install -y python3-pip postgresql-client jq nodejs yarn bc git imagemagick brotli wkhtmltopdf bash openssh-client libgtk2.0-0 libgtk-3-0 libgbm-dev libnotify-dev libgconf-2-4 libnss3 libxss1 libasound2 libxtst6 xauth xvfb

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
