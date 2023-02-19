FROM debian:latest

EXPOSE 22

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -qq update
RUN apt-get -qq install openssh-server
RUN apt-get -qq install krb5-user
RUN apt-get -qq install vim iputils-ping net-tools
RUN apt-get -qq clean

# configuration for the SSH server
RUN mkdir -p /run/sshd
RUN ssh-keygen -A
COPY sshd_config /etc/ssh/sshd_config
# configuration for the SSH client
COPY ssh_config /etc/ssh/ssh_config 

