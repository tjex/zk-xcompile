FROM --platform=linux/arm64 golang:1.21
LABEL os=linux
LABEL arch=arm64

ENV GOOS=linux
ENV GOARCH=arm64
ENV CGO_ENABLED=1
ENV CC=aarch64-linux-gnu-gcc
ENV PATH="/go/bin/${GOOS}_${GOARCH}:${PATH}"
ENV PKG_CONFIG_PATH=/usr/lib/aarch64-linux-gnu/pkgconfig

RUN dpkg --add-architecture arm64 \
 && apt update \
 && apt install -y --no-install-recommends \
        pkg-config \
        gcc-aarch64-linux-gnu \
        libc6-dev-arm64-cross \
 && rm -rf /var/lib/apt/lists/*
