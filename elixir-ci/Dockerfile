FROM hexpm/elixir:1.12.3-erlang-24.1.2-alpine-3.14.2

RUN apk add --no-cache curl python3 py3-pip postgresql-client jq nodejs-current~=16 yarn bc git build-base imagemagick brotli wkhtmltopdf bash openssh-client docker-cli xvfb

RUN apk upgrade --no-cache

RUN pip install pip awscli virtualenv requests boto3 --upgrade

RUN apk -X http://dl-cdn.alpinelinux.org/alpine/edge/testing add github-cli

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
