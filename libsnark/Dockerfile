FROM ubuntu:18.04
MAINTAINER xiabee

WORKDIR /app

ENV TZ "Asia/Shanghai"
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get install -y --no-install-recommends wget

RUN apt install -y --no-install-recommends build-essential \
    cmake \
    git \
    libgmp3-dev \
    libprocps-dev \
    python3-markdown \
    libboost-program-options-dev \
    libssl-dev \
    python3 \
    pkg-config

COPY lib lib

WORKDIR /app/lib/

RUN mkdir build

WORKDIR /app/lib/build

RUN cmake ..
RUN make