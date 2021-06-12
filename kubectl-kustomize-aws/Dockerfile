FROM alpine:3.12.1

ENV GLIBC_VER=2.31-r0
ENV KUBE_VERSION=1.19.0
ENV KUSTOMIZE_VERSION=3.8.7

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"
RUN apk update
RUN apk --no-cache add curl bash sudo shadow which nodejs-current readline linux-pam

RUN echo "Install Kubectl && Kustomize && AWS" && \
    apk --no-cache add \
        gettext \
        binutils \
        curl \
    &&  curl -L https://storage.googleapis.com/kubernetes-release/release/v${KUBE_VERSION}/bin/linux/amd64/kubectl -o /usr/bin/kubectl \
    &&  chmod +x /usr/bin/kubectl \
    &&  curl -sLO https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2Fv${KUSTOMIZE_VERSION}/kustomize_v${KUSTOMIZE_VERSION}_linux_amd64.tar.gz \
    &&  tar -xvzf kustomize_v${KUSTOMIZE_VERSION}_linux_amd64.tar.gz  \
    &&  mv kustomize /usr/bin/kustomize \
    && curl -sL https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub -o /etc/apk/keys/sgerrand.rsa.pub \
    && curl -sLO https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VER}/glibc-${GLIBC_VER}.apk \
    && curl -sLO https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VER}/glibc-bin-${GLIBC_VER}.apk \
    && apk add --no-cache \
        glibc-${GLIBC_VER}.apk \
        glibc-bin-${GLIBC_VER}.apk \
    && curl -sL https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip -o awscliv2.zip \
    && unzip awscliv2.zip \
    && aws/install \
    && rm -rf \
        awscliv2.zip \
        aws \
        /usr/local/aws-cli/v2/*/dist/aws_completer \
        /usr/local/aws-cli/v2/*/dist/awscli/data/ac.index \
        /usr/local/aws-cli/v2/*/dist/awscli/examples \
    && apk --no-cache del \
        binutils \
    && rm glibc-${GLIBC_VER}.apk \
    && rm glibc-bin-${GLIBC_VER}.apk \
    && rm -rf /var/cache/apk/* \
    && echo "Done install Kubectl && Kustomize && AWS"