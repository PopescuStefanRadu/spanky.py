FROM archlinux/base

RUN pacman -Sy && \
    pacman -S --noconfirm \
    git \
    wget \
    libqalculate \
    liblqr \
    tar \
    gcc \
    awk \
    make \
    imagemagick

# Install go
RUN mkdir -p /opt && cd /opt && \
    wget https://dl.google.com/go/go1.12.5.linux-amd64.tar.gz -O go.tar.gz && \
    tar -zxf go.tar.gz

ENV GOPATH="/opt/goproj"
ENV PATH="${PATH}:/opt/go/bin:/opt/goproj/bin"

# Install yeetgif
RUN go get -u github.com/sgreben/yeetgif/cmd/gif

ADD files/startup.sh /startup.sh