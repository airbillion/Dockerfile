FROM alpine:latest
ENV EDGE_REPOSITORY=http://dl-cdn.alpinelinux.org/alpine/edge/main
RUN apk update --repository $EDGE_REPOSITORY \
    && apk --no-cache add ca-certificates \
    && apk add py-pip \
    && apk add ffmpeg --repository $EDGE_REPOSITORY \
    && pip install -I flexget transmissionrpc \
    && mkdir -p /root/.flexget \
    && touch /root/.flexget/config.yml
RUN pip install --upgrade pip
RUN pip install --upgrade youtube-dl
RUN pip install --upgrade flexget
CMD ["/usr/bin/flexget", "--loglevel", "debug", "daemon", "start"]