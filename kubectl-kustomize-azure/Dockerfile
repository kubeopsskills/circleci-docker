FROM alpine:3.13.4

ENV KUBE_VERSION=1.19.0
ENV KUSTOMIZE_VERSION=3.8.7

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"
RUN apk update
RUN apk --no-cache add sudo shadow which nodejs-current readline linux-pam

RUN echo "Install AZURE CLI" \
    && apk --no-cache add curl bash npm py3-pip \
    && apk --no-cache add --virtual=build make gcc musl-dev python3-dev libffi-dev openssl-dev cargo \
    && pip3 install azure-cli \
    && apk del --purge build \
    && echo "Done install AZURE CLI"

RUN echo "Install Kubectl & Kustomize" \
    && curl -L https://storage.googleapis.com/kubernetes-release/release/v${KUBE_VERSION}/bin/linux/amd64/kubectl -o /usr/bin/kubectl \
    && chmod +x /usr/bin/kubectl \
    && curl -sLO https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2Fv${KUSTOMIZE_VERSION}/kustomize_v${KUSTOMIZE_VERSION}_linux_amd64.tar.gz \
    && tar -xvzf kustomize_v${KUSTOMIZE_VERSION}_linux_amd64.tar.gz  \
    && mv kustomize /usr/bin/kustomize \
    && echo "Done install Kubectl & Kustomize"

RUN rm -rf /var/cache/apk/* && rm -rf /tmp/* \