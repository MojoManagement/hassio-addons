ARG BUILD_FROM
FROM $BUILD_FROM

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

# Install requirements for add-on
RUN apk update && apk add --no-cache \
    avahi \
    bash jq iw net-tools \
    sudo busybox-extras \
    hostapd networkmanager-cli iptables \
    linux-firmware-other \
    linux-firmware-ath6k \
    linux-firmware-ath10k \
    linux-firmware-ath9k_htc \
    git build-base linux-headers dkms && \
    rm -rf /var/cache/apk/*

# Install rtl8188eu driver
RUN git clone https://github.com/ivanovborislav/rtl8188eu && \
    cd rtl8188eu && \
    make && make install && \
    modprobe r8188eu

# Copy configuration files
COPY hostapd.conf /
COPY udhcpd.conf /etc/udhcpd.conf
COPY run.sh /

# Make the script executable
RUN chmod a+x /run.sh

# Run the script
CMD [ "/run.sh" ]
