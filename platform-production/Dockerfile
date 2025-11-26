ARG ALPINE_VERSION
FROM alpine:${ALPINE_VERSION}

RUN apk add --no-cache imagemagick curl postgresql14-client chromium bash jq openssl util-linux nodejs

RUN apk upgrade --no-cache
