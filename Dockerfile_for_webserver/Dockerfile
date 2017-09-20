FROM ubuntu:14.04
MAINTAINER Ronny Jiang "set@aliyun.com"
ENV REFRESHED_AT 2017-06-22

USER root

#sync time
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

#update sources and install git vim  and nginx
ADD sources.list /etc/apt/sources.list
RUN apt-get update
RUN apt-get -y install git
RUN apt-get -y install vim
RUN apt-get -y install nginx

########start install software#########

RUN useradd --create-home ronny
RUN gpasswd -a ronny root
RUN /bin/echo -e "LANG=\"en_US.UTF-8\"" >/etc/default/local
USER ronny
ENV HOME /home/ronny
EXPOSE 80 443
CMD ["bash"]

