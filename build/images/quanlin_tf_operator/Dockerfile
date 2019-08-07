FROM registry.access.redhat.com/ubi8/ubi:latest

ARG GOLANG_VERSION=1.8.3
ENV GOROOT=/usr/local/go PATH=$PATH:/usr/local/go/bin

RUN if [ "$(uname -m)" = "ppc64le" ]; then \
        curl -fksSL https://dl.google.com/go/go$GOLANG_VERSION.linux-ppc64le.tar.gz | tar -xz -C /usr/local/; \
    else \
        curl -fksSL https://dl.google.com/go/go$GOLANG_VERSION.linux-amd64.tar.gz | tar -xz -C /usr/local/; \
    fi


RUN mkdir -p /opt/kubeflow

COPY tf-operator.v1 /opt/kubeflow

RUN chmod a+x /opt/kubeflow/tf-operator.v1

ENTRYPOINT ["/opt/kubeflow/tf-operator.v1"]
