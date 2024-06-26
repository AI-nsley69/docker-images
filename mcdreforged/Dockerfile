FROM eclipse-temurin:21-alpine

# Install python/pip
ENV PYTHONUNBUFFERED=1
RUN apk add --update --no-cache python3 py3-pip python3-dev musl-dev linux-headers gcc && ln -sf python3 /usr/bin/python
# RUN python3 -m ensurepip
RUN pip3 install --no-cache --upgrade --break-system-packages pip mcdreforged
RUN adduser -D -h /home/container container

WORKDIR /home/container

ENV USER=container HOME=/home/container

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]