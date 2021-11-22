FROM docker:20.10.7-git

ARG YQ_VERSION=v4.14.2

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"
RUN apk update
RUN apk --no-cache add sudo shadow which nodejs-current readline linux-pam

RUN echo "Install AZURE CLI" \
    && apk --no-cache add curl bash npm py3-pip
RUN apk --no-cache add --virtual=build make gcc musl-dev python3-dev libffi-dev openssl-dev cargo \
    && pip3 install azure-cli \
    && apk del --purge build \
    && rm -rf /var/cache/apk/* && rm -rf /tmp/* \
    && echo "Done install AZURE CLI"

RUN wget -O /usr/bin/yq "https://github.com/mikefarah/yq/releases/download/${YQ_VERSION}/yq_linux_amd64"
RUN chmod ugo+x /usr/bin/yq