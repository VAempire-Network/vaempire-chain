FROM ubuntu:20.04
ARG release_version=LATEST_VAEMPIRE_RELEASE
RUN apt-get -y update && apt-get -y install libssl-dev libudev-dev curl
RUN curl -sSf https://raw.githubusercontent.com/vaempire-network/vaempire-chain/develop/install/vaempire-install-init.sh | sh -s - LATEST_VAEMPIRE_RELEASE
ENV PATH="/root/.local/share/vaempire/install/active_release/bin":"$PATH"
COPY entrypoint.sh entrypoint.sh
ENTRYPOINT [ "/usr/bin/sh","-c", "./entrypoint.sh" ]
