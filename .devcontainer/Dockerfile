ARG BASEDEV_VERSION=v0.3.0

FROM qmcgaw/basedevcontainer:${BASEDEV_VERSION}-alpine

# https://github.com/Quantisan/docker-clojure/blob/f651209e1815a9dc5382ad7d40f5e5058ab01c66/target/openjdk-11-slim-buster/lein/Dockerfile
RUN apk update && \
apk add openjdk11 && \
apk add gnupg && \
apk add util-linux && \
apk add leiningen --repository=http://dl-cdn.alpinelinux.org/alpine/edge/testing/ && \
rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME=/usr/lib/jvm/java-11-openjdk/bin/java
ENV PATH=$JAVA_HOME/bin:$PATH

RUN wget -q https://github.com/clojure-lsp/clojure-lsp/releases/download/2021.08.24-14.41.56/clojure-lsp && \
mv clojure-lsp /usr/local/bin/clojure-lsp && \
chmod 0755 /usr/local/bin/clojure-lsp
