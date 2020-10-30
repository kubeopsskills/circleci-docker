FROM ghcr.io/kubeopsskills/levis:1.0.1-alpha
RUN apt-get update && apt-get install git build-essential ruby ruby-dev rubygems ruby-bundler apt-transport-https gnupg2 -y \
    && curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg \ 
    | apt-key add - \
    && echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" \
    | tee -a /etc/apt/sources.list.d/kubernetes.list \
    && apt-get update &&  apt-get install -y kubectl
RUN gem install krane --no-document
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
ENTRYPOINT [ "/bin/bash" ]