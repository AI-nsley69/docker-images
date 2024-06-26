FROM ghcr.io/graalvm/graalvm-ce

COPY ./packages ./packages

RUN rpm -i ./packages/* && useradd -md /home/container container && rm -rf ./packages

USER container

WORKDIR /home/container

ENV USER=container HOME=/home/container LD_PRELOAD=/usr/lib64/libjemalloc.so.2

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]