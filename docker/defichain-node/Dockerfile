FROM ubuntu:focal

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y \
    automake \
    autotools-dev \
    bsdmainutils \
    build-essential \
    curl \
    libboost-chrono-dev \
    libboost-filesystem-dev \
    libboost-system-dev \
    libboost-test-dev \
    libboost-thread-dev \
    libevent-dev \
    libminiupnpc-dev \
    libssl-dev \
    libtool \
    libzmq3-dev \
    pkg-config \
    python3 \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /usr/src/defichain && \
    cd /usr/src/defichain && \
    curl -L  https://github.com/DeFiCh/ain/archive/v1.7.2.tar.gz > defichain.tar.gz && \
    tar xvzf defichain.tar.gz && \
    cd ain-1.7.2/depends && \
    make HOST=aarch64-linux-gnu

RUN cd /usr/src/defichain/ain-1.7.2 && \
    ./autogen.sh && \
    ./configure --prefix=$PWD/depends/aarch64-linux-gnu --enable-glibc-back-compat --enable-reduce-exports LDFLAGS=-static-libstdc++ && \
    make

ENV PATH=/usr/src/defichain/ain-1.7.2/src:$PATH

CMD ["defid"]
