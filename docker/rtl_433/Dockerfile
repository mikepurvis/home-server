# sudo docker run -t -i --device=/dev/bus/usb/008/002 <image> -f 344975000

FROM lsiobase/ubuntu:bionic

LABEL maintainer="Mike P <mike@uwmike.com>"

ENV VERSION 1.0
ENV APP_VERSION d362397a4ba29b104bf8b925c9efedd7047046ad

RUN apt-get update && \
    apt-get install -y \
            git build-essential autoconf libtool \
            libusb-1.0.0-dev librtlsdr-dev rtl-sdr autoconf cmake pkg-config

WORKDIR /tmp

RUN git clone https://github.com/merbanan/rtl_433.git --depth=1 && \
    cd rtl_433 && \
    git checkout $APP_VERSION && \
    mkdir build && \
    cd build && \
    cmake .. && \
    make && \
    make install

ENTRYPOINT ["rtl_433"]
