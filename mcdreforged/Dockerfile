FROM ghcr.io/graalvm/graalvm-ce

RUN useradd -md /home/container container && yum install -y python3-pip && pip3 install --upgrade pip && pip3 install mcdreforged

WORKDIR /home/container

ENV USER=container HOME=/home/container

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]