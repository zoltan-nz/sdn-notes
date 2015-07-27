# Creating a Vagrant image


Source: https://registry.hub.docker.com/u/osrg/ryu/dockerfile/raw

```
# Ryu SDN Framework
#
# VERSION 0.0.1

FROM ubuntu:15.04

MAINTAINER FUJITA Tomonori <fujita.tomonori@lab.ntt.co.jp>

RUN apt-get update
RUN apt-get install -qy --no-install-recommends python-setuptools python-pip python-eventlet python-lxml python-msgpack unzip wget

ENV HOME /root
WORKDIR /root

RUN wget --no-check-certificate https://github.com/osrg/ryu/archive/master.zip
RUN unzip master.zip
RUN cd ryu-master && python setup.py install
```

Source: https://raw.githubusercontent.com/openvapour/valve/master/docker/Dockerfile

```
FROM osrg/ryu

RUN \
  apt-get update && \
  apt-get install -qy --no-install-recommends git python-yaml

RUN \
  git clone https://github.com/openvapour/valve /srv/valve

VOLUME ["/etc/valve/"]

RUN \
  ln -s /etc/valve/valve.yaml /srv/valve/

WORKDIR /srv/valve

CMD ["ryu-manager", "valve.py"]

EXPOSE 6633
EXPOSE 8080
```