ARG ELIXIR_VERSION
ARG ERLANG_VERSION
ARG DEBIAN_VERSION

FROM hexpm/elixir:${ELIXIR_VERSION}-erlang-${ERLANG_VERSION}-debian-${DEBIAN_VERSION}

ARG DEBIAN_FRONTEND=noninteractive
RUN apt update -y
RUN apt upgrade -y
RUN apt dist-upgrade -y

RUN apt install -y curl bash ca-certificates gnupg

RUN apt update -y

RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - &&\
    apt-get install -y nodejs

RUN apt install -y --no-install-recommends \
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
