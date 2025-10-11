FROM mcr.microsoft.com/devcontainers/typescript-node:22
COPY debconf.config.dat /root/debconf.config.dat
RUN \
    export DEBIAN_FRONTEND=noninteractive DEBCONF_DB_FALLBACK='File{/root/debconf.config.dat}'; \
    sed -i~ -e 's/ main *$/ main contrib non-free non-free-firmware/' /etc/apt/sources.list.d/debian.sources && \
    apt-get update -qy && \
    apt-get install -qy \
        google-android-cmdline-tools-9.0-installer \
        google-android-platform-33-installer \
        google-android-ndk-r25c-installer \
        && \
    apt-get clean -qy
ENV ANDROID_HOME=/usr/lib/android-sdk
