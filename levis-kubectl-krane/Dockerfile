# https://github.com/Shopify/krane

FROM ghcr.io/kubeopsskills/levis:1.3.0-beta
RUN apt-get update && apt-get install git build-essential ruby rubygems-integration ruby-dev rubygems ruby-bundler apt-transport-https gnupg2 -y \
    && curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg \ 
    | apt-key add - \
    && echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" \
    | tee -a /etc/apt/sources.list.d/kubernetes.list
RUN gem install activesupport -v 6.1.4.4
RUN gem install rake
RUN gem install rainbow
RUN gem install krane --no-document -v 2.1.3
RUN apt-get update &&  apt-get install -y kubectl
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
ENTRYPOINT [ "/bin/bash" ]