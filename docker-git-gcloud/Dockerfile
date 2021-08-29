FROM docker:20.10.7-git

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"
RUN apk update
RUN apk --no-cache add sudo shadow which nodejs-current readline linux-pam

RUN echo "Install GCLOUD CLI" \
    && apk --no-cache add curl bash npm py3-pip \
    && rm -rf /var/cache/apk/* && rm -rf /tmp/* 

RUN curl -sSL https://sdk.cloud.google.com | bash

ENV PATH $PATH:/root/google-cloud-sdk/bin

RUN echo "Done install GCLOUD CLI"