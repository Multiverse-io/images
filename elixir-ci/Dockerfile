FROM hexpm/elixir:1.12.2-erlang-24.0.4-alpine-3.14.0

RUN apk add --no-cache curl python3 py3-pip postgresql-client jq nodejs-current~=16 yarn bc git build-base imagemagick brotli wkhtmltopdf bash openssh-client docker-cli

RUN apk upgrade --no-cache

RUN pip install awscli virtualenv requests boto3 --upgrade

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
