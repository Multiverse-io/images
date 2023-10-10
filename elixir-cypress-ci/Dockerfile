FROM hexpm/elixir:1.14.2-erlang-25.1.2-debian-bullseye-20221004-slim

ARG DEBIAN_FRONTEND=noninteractive
RUN apt update -y
RUN apt upgrade -y
RUN apt dist-upgrade -y

RUN apt install -y curl bash ca-certificates gnupg

RUN mkdir -p /etc/apt/keyrings && \
    curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg && \
    echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_18.x nodistro main" | tee /etc/apt/sources.list.d/nodesource.list

RUN apt update -y

RUN apt install -y --no-install-recommends \
    nodejs \
    openssh-client \
    postgresql-client \
    make \
    gcc \
    git \
    imagemagick \

    # cypress deps from here https://docs.cypress.io/guides/continuous-integration/introduction#Dependencies

    libgtk2.0-0 \
    libgtk-3-0 \
    libgbm-dev \
    libnotify-dev \
    libgconf-2-4 \
    libnss3 \
    libxss1 \
    libasound2 \
    libxtst6 \
    xauth \
    xvfb

# Install yarn using corepack
RUN corepack enable

RUN mix local.hex --force
RUN mix local.rebar --force

CMD ["iex"]
