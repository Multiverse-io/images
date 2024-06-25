ARG ELIXIR_VERSION
ARG ERLANG_VERSION
ARG DEBIAN_VERSION

FROM hexpm/elixir:${ELIXIR_VERSION}-erlang-${ERLANG_VERSION}-debian-${DEBIAN_VERSION}

ARG DEBIAN_FRONTEND=noninteractive
RUN apt update -y
RUN apt upgrade -y
RUN apt dist-upgrade -y

RUN apt install -y curl bash ca-certificates gnupg python3-full

RUN mkdir -p /etc/apt/keyrings && \
    curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg && \
    echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_18.x nodistro main" | tee /etc/apt/sources.list.d/nodesource.list

RUN apt update -y

RUN apt install -y --no-install-recommends python3-pip postgresql-client-15 jq nodejs yarn bc git build-essential imagemagick brotli chromium bash openssh-client docker.io xvfb tar awscli virtualenv

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
