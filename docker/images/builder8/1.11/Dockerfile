FROM opennetworklinux/builder8:1.10
MAINTAINER Jeffrey Townsend <jeffrey.townsend@arista.com>

#
# The purpose of this image is to correct the problem in the docker_shell utility described here:
#
# commit d2fbc6ce14f6f1f693d03e2de448620e91842c8c
# Author: Jeffrey Townsend <jeffrey.townsend@bigswitch.com>
# Date:   Mon Mar 23 18:02:46 2020 -0700
#
#    The files in /etc/sudoers.d are ignored if they contain periods. If a invoking username contains a period then the sudo feature is broken and you cannot build.
#
RUN echo "deb http://archive.debian.org/debian/ jessie contrib main non-free" | tee /etc/apt/sources.list
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get upgrade -y
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install build-essential libmnl0 libmnl-dev -y

COPY docker_shell /bin/docker_shell
COPY container-id /bin/container-id
