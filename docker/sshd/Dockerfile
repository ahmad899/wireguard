FROM alpine:3.20.2
USER root
RUN set -eux; \
    apk update; apk add  \
    dumb-init \
    openssh;
COPY vulcan-bastion-host.pem /root/.ssh/.keys/vulcan-bastion-host.pem
COPY config /root/.ssh/config
EXPOSE 443
CMD ["dumb-init", "ssh", "-4", "-NL", "10.8.1.3:443::address:443", "your-host"]
