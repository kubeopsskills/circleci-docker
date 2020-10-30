FROM docker:19.03.13-git

RUN echo "Install AWS" && \
    apk add -q --no-cache bash build-base ca-certificates curl gettext git libffi-dev linux-headers musl-dev openldap-dev openssh-client python3-dev gcc libffi-dev libressl-dev make rsync tzdata groff && \
    python3 -m ensurepip && \
    pip3 install --no-cache --upgrade pip setuptools wheel && \
    pip -q install pipenv==3 awscli boto3 PyYAML && \
    echo "Done install AWS"