ARG ALPINE_VERSION
FROM lacework/datacollector:latest-sidecar AS lacework-collector

ARG ALPINE_VERSION
FROM alpine:${ALPINE_VERSION}

RUN apk add --no-cache imagemagick curl postgresql13-client chromium bash jq openssl util-linux nodejs libvpx postgresql-common=1.2-r1 yaml=2.2.4 libuv=1.48.0
RUN apk upgrade --no-cache

COPY --from=lacework-collector /var/lib/lacework-backup /var/lib/lacework-backup

# install the lacework datacollector binary
RUN mkdir -p /var/lib/lacework && \
        mv /var/lib/lacework-backup/*/datacollector-musl /var/lib/lacework/datacollector && \
        chmod +x /var/lib/lacework/datacollector && \
        # datacollector needs to run as root so set setuid bit
        chmod u+s /var/lib/lacework/datacollector && \
        rm -rf /var/lib/lacework-backup
