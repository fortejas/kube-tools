FROM alpine:3.10.2

ARG kubectl_version=v1.13.11
ARG version=0.1.0

LABEL Maintainer 'Jason Forte <fortejas@amazon.com>'
LABEL Version ${version}

RUN apk update \
    && apk add \
    bind-tools==9.14.3-r0 \
    curl==7.66.0-r0

RUN wget -O /usr/bin/kubectl https://storage.googleapis.com/kubernetes-release/release/${kubectl_version}/bin/linux/amd64/kubectl \
    && chmod +x /usr/bin/kubectl

RUN rm -rf /var/cache/apk/*
