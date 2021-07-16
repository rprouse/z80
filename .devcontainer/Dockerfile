# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.187.0/containers/alpine/.devcontainer/base.Dockerfile

# [Choice] Alpine version: 3.13, 3.12, 3.11, 3.10
ARG VARIANT="3.12"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-alpine-${VARIANT}

# Install additional packages.
RUN apk update \
    && apk add --no-cache git make gcc g++ libc-dev libusb-dev pkgconfig

RUN cd /opt && \
    git clone --depth 1 --branch v1.18.2 https://github.com/z00m128/sjasmplus && \
    cd sjasmplus && \
    make all && \
    make install
