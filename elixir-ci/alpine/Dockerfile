ARG ELIXIR_VERSION
ARG ERLANG_VERSION
ARG ALPINE_VERSION

FROM hexpm/elixir:${ELIXIR_VERSION}-erlang-${ERLANG_VERSION}-alpine-${ALPINE_VERSION}

RUN apk add --no-cache curl python3 py3-pip postgresql13-client jq nodejs~=20 \
yarn bc git build-base imagemagick brotli chromium bash openssh-client docker-cli xvfb libc6-compat tar

RUN apk upgrade --no-cache

RUN pip install -U pip

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
