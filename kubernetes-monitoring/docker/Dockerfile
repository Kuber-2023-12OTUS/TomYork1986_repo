ARG ALPINE_TAG=latest
FROM alpine:${ALPINE_TAG}

LABEL maintainer="Artem Obidchenko" \
    description="A simple docker image with web-server installed."

RUN apk -U upgrade \
    && apk add --no-cache \
        bash \
        bash-completion \
        bind-tools \
        ca-certificates \
        coreutils \
        curl \
        nginx \
        openssl \
        shadow \
    && rm -rf /var/cache/apk/* \
    && usermod -u 1001 nginx

COPY nginx.conf /etc/nginx/nginx.conf
COPY index.html /app/index.html

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
