FROM hexpm/elixir:1.13.4-erlang-25.0.2-alpine-3.16.0

RUN apk add --no-cache curl python3 py3-pip postgresql13-client jq nodejs~=16 yarn bc git build-base imagemagick brotli chromium bash openssh-client docker-cli xvfb libc6-compat

RUN apk upgrade --no-cache

RUN pip install -U pip

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
