FROM alpine:3.20.2
USER root
RUN set -eux; \
    apk update; apk add  \
    dumb-init \
    openssh;
COPY vulcan-bastion-host.pem /root/.ssh/.keys/vulcan-bastion-host.pem
COPY config /root/.ssh/config
EXPOSE 443
CMD ["dumb-init", "ssh", "-4", "-NL", "10.8.1.3:443:3486D1560C6A8FDF52ED2E8F98B6EF25.gr7.us-east-1.eks.amazonaws.com:443", "vulcan-dev-baston"]
