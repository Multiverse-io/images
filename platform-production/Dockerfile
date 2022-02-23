FROM lacework/datacollector:latest-sidecar AS lacework-collector

FROM alpine:3.15.0

RUN apk add --no-cache imagemagick curl postgresql-client chromium bash jq ttf-dejavu ttf-droid ttf-freefont ttf-liberation openssl util-linux

RUN apk upgrade --no-cache

COPY --from=lacework-collector /var/lib/lacework-backup /var/lib/lacework-backup

# install the lacework datacollector binary
RUN mkdir -p /var/lib/lacework && \
        mv /var/lib/lacework-backup/*/datacollector-musl /var/lib/lacework/datacollector && \
        chmod +x /var/lib/lacework/datacollector && \
        # datacollector needs to run as root so set setuid bit
        chmod u+s /var/lib/lacework/datacollector && \
        rm -rf /var/lib/lacework-backup
