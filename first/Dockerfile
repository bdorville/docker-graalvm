FROM alpine:3.7

ENV GRAALVM_VERSION 1.0.0-rc1
ENV GRAALVM_HOME /usr/graalvm-$GRAALVM_VERSION

RUN apk update && apk upgrade && \
    apk add --no-cache curl bash openssl unzip tar && \
    curl -L "https://github.com/oracle/graal/releases/download/vm-${GRAALVM_VERSION}/graalvm-ce-${GRAALVM_VERSION}-linux-amd64.tar.gz" -o graalvm.tar.gz && \
    tar -xf graalvm.tar.gz -C /usr/ && \
    chown -R root:root $GRAALVM_HOME

WORKDIR $GRAALVM_HOME
CMD ["bin/java", "-version"]
