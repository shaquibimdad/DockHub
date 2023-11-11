FROM ubuntu:22.04

ENV DEBIAN_FRONTEND="noninteractive" TZ="Asia/Kolkata"

RUN apt-get update && apt-get -y install \
    build-essential \
    bc \
    bison \
    bsdmainutils \
    libtinfo5 \
    cpio \
    ccache \
    cmake \
    curl \
    flex \
    g++ \
    gcc \
    git \
    lcov \
    libkrb5-dev \
    libmaxminddb-dev \
    libpcap-dev \
    libssl-dev \
    make \
    python3 \
    python3-dev \
    python3-pip ruby \
    sqlite3 \
    swig \
    unzip \
    wget \
    zlib1g-dev && \
    apt autoclean && \
    rm -rf /var/lib/apt/lists/*

RUN git config --global core.protectNTFS false

RUN git clone --depth 1 https://github.com/pyenv/pyenv.git ~/.pyenv

ENV PYENV_ROOT /root/.pyenv
ENV PATH $PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH

RUN pyenv install 2.7.18
RUN pyenv global 2.7.18
RUN pyenv rehash
