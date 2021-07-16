# Using an Ubuntu container because I can't get sjasmplus to build in Alpine
ARG VARIANT=focal
FROM mcr.microsoft.com/vscode/devcontainers/base:${VARIANT}

# Install additional packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends git make gpg gcc g++ libc-dev libusb-dev libusb-1.0-0-dev pkg-config

RUN cd /opt && \
    git clone --depth 1 --branch v1.18.2 https://github.com/z00m128/sjasmplus && \
    cd sjasmplus && \
    make all && \
    make install

RUN cd /opt && \
    git clone --depth 1 --branch 0.5 https://gitlab.com/DavidGriffith/minipro.git && \
    cd minipro && \
    make all && \
    make install
