ARG ELIXIR_VERSION
ARG ERLANG_VERSION
ARG ALPINE_VERSION

FROM hexpm/elixir:${ELIXIR_VERSION}-erlang-${ERLANG_VERSION}-alpine-${ALPINE_VERSION}

RUN apk add --no-cache curl python3 py3-pip postgresql13-client jq nodejs \
yarn bc git build-base imagemagick brotli chromium bash openssh-client docker-cli xvfb libc6-compat tar postgresql-common=1.2-r1 yaml=2.2.4 libuv=1.48.0

RUN apk upgrade --no-cache

RUN pip install -U pip

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
