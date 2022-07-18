FROM docker:20.10.16-git

ARG APL_VERSION=v3.16
ARG YQ_VERSION=v4.24.5
ARG GLIBC_VER=2.35-r0 

RUN echo "@edge https://dl-cdn.alpinelinux.org/alpine/edge/main" >> /etc/apk/repositories

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"
RUN apk add -X "https://dl-cdn.alpinelinux.org/alpine/${APL_VERSION}/main" -u alpine-keys
RUN apk update
RUN echo "Install Node"
RUN apk add --no-cache  sudo shadow which nodejs-current@edge npm@edge readline linux-pam
RUN apk --no-cache add nodejs yarn --repository=http://dl-cdn.alpinelinux.org/alpine/edge/community
RUN apk add aws-cli

RUN wget -O /usr/bin/yq "https://github.com/mikefarah/yq/releases/download/${YQ_VERSION}/yq_linux_amd64"
RUN chmod ugo+x /usr/bin/yq