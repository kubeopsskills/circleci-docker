FROM docker:19.03.13-git

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"
RUN apk update
RUN apk --no-cache add sudo shadow which nodejs-current readline linux-pam

RUN echo "Install AZURE CLI" \
    && apk --no-cache add curl bash npm py3-pip \
    && apk --no-cache add --virtual=build make gcc musl-dev python3-dev libffi-dev openssl-dev cargo \
    && pip3 install azure-cli \
    && apk del --purge build \
    && rm -rf /var/cache/apk/* && rm -rf /tmp/* \
    && echo "Done install AZURE CLI"