FROM ubuntu:16.04

RUN apt-get update && apt-get install -y \
    curl \
    zip

# Install kubectl
RUN curl -Lo /usr/local/bin/kubectl https://storage.googleapis.com/kubernetes-release/release/v1.8.7/bin/linux/amd64/kubectl
RUN chmod +x /usr/local/bin/kubectl

# Install Helm
RUN curl -Lo /tmp/helm-linux-amd64.tar.gz https://kubernetes-helm.storage.googleapis.com/helm-v2.8.2-linux-amd64.tar.gz
RUN tar -xvf /tmp/helm-linux-amd64.tar.gz -C /tmp/
RUN chmod +x  /tmp/linux-amd64/helm && mv /tmp/linux-amd64/helm /usr/local/bin/

WORKDIR /data

COPY ./input/ .

LABEL source=git@github.com:mszostok/re-e2e-tester.git

ENTRYPOINT ["./testing.sh"]