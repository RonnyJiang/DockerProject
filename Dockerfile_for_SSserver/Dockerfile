FROM ubuntu:14.04
MAINTAINER Ronny Jiang "set@aliyun.com"
ENV REFRESHED_AT 2017-09-20

USER root

#sync time
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

#update sources and install vim git python-pip and shadowsocks.
ADD sources.list /etc/apt/sources.list
RUN apt-get update
RUN apt-get -y install git
RUN apt-get -y install vim
RUN apt-get -y install python-pip
RUN pip install git+https://github.com/shadowsocks/shadowsocks.git@master
ADD shadowsocks.json /etc/shadowsocks.json
########start install software#########

RUN /bin/echo -e "LANG=\"en_US.UTF-8\"" >/etc/default/local
USER root
ENV HOME /root
CMD ["bash"]

