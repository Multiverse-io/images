FROM hexpm/elixir:1.14.5-erlang-26.1.2-alpine-3.18.4

RUN apk add --no-cache curl python3 py3-pip postgresql13-client jq nodejs~=18 yarn bc git build-base imagemagick brotli chromium bash openssh-client docker-cli xvfb libc6-compat tar

RUN apk upgrade --no-cache

RUN pip install -U pip

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
