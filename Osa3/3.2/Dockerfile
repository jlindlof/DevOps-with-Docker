FROM alpine
RUN apk add \
    ffmpeg \
    gcc \
    libxml2-dev \
    libxslt-dev \
    musl-dev \
    php7 \
    php7-bcmath \
    php7-curl \
    php7-openssl \
    php7-simplexml \
    python3 \
    python3-dev \
    rtmpdump \
    wget \
    youtube-dl && \
    pip3 install --upgrade pip yle-dl && \
    adduser -D jan

WORKDIR /tmp
USER jan
ENTRYPOINT ["yle-dl"]
