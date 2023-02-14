FROM ghcr.io/graalvm/graalvm-ce

MAINTAINER AI-nsley69

COPY ./packages ./packages

RUN microdnf install ./packages/* && microdnf clean && useradd -md /home/container container && rm -rf ./packages

USER container

WORKDIR /home/container

ENV USER=container HOME=/home/container LD_PRELOAD=/usr/lib/libjemalloc.so.2

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]