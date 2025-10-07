FROM mcr.microsoft.com/devcontainers/typescript-node:22
RUN \
    sudo sed -i~ -e 's/ main *$/ main contrib non-free non-free-firmware/' /etc/apt/sources.list.d/debian.sources && \
    sudo apt-get update -qy && \
    sudo apt-get install -qy android-sdk google-android-platform-33-installer && \
    sudo apt-get clean -qy
