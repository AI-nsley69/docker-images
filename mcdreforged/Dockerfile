FROM ghcr.io/graalvm/graalvm-ce

MAINTAINER AI-nsley69

RUN useradd -md /home/container container && pip3 install mcdreforged

WORKDIR /home/container

ENV USER=container HOME=/home/container

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]