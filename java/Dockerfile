FROM ghcr.io/graalvm/graalvm-ce

MAINTAINER AI-nsley69

RUN microdnf --enablerepo=oraclelinux-release-el9 && microdnf install jemalloc && microdnf clean && useradd -md /home/container container

USER container

WORKDIR /home/container

ENV USER=container HOME=/home/container LD_PRELOAD=/usr/lib/libjemalloc.so.2

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]