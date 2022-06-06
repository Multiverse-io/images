FROM hexpm/elixir:1.13.3-erlang-24.3.4-alpine-3.15.3

RUN apk add --no-cache curl python3 py3-pip postgresql13-client jq nodejs~=16 yarn bc git build-base imagemagick brotli chromium bash openssh-client docker-cli xvfb libc6-compat
RUN apk add rabbitmq-server --repository=http://dl-cdn.alpinelinux.org/alpine/edge/testing

RUN apk upgrade --no-cache

RUN pip install -U pip

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN rabbitmq-server &

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
