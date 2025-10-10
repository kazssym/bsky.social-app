FROM mcr.microsoft.com/devcontainers/typescript-node:22
RUN \
    export DEBIAN_FRONTEND=noninteractive; \
    sed -i~ -e 's/ main *$/ main contrib non-free non-free-firmware/' /etc/apt/sources.list.d/debian.sources && \
    apt-get update -qy && \
    apt-get install -qy android-sdk && \
    apt-get clean -qy
COPY debconf.config.dat /root/debconf.config.dat
RUN \
    export DEBIAN_FRONTEND=noninteractive DEBCONF_DB_FALLBACK='File{/root/debconf.config.dat}'; \
    apt-get install -qy google-android-platform-33-installer google-android-ndk-r25c-installer && \
    apt-get clean -qy
ENV \
    ANDROID_HOME=/usr/lib/android-sdk
