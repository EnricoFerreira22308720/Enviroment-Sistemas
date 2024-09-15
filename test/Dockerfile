FROM ubuntu:20.04

RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    gdb \
    gcc \
    g++ \
    clang \
    git \
    curl \
    wget \
    vim \
    openssh-server \
    sudo

RUN useradd -ms /bin/bash devuser && echo "devuser:password" | chpasswd && adduser devuser sudo

RUN mkdir /var/run/sshd
RUN echo "devuser ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
