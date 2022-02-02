FROM hexpm/elixir:1.13.2-erlang-24.2.1-alpine-3.14.3

RUN apk add --no-cache curl python3 py3-pip postgresql-client jq nodejs-current~=16 yarn bc git build-base imagemagick brotli wkhtmltopdf bash openssh-client docker-cli xvfb

RUN apk upgrade --no-cache

RUN pip install -U pip

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
