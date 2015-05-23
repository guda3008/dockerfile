# sshd dockerfile
#
FROM centos:centos7
MAINTAINER yaofh <m1375500@126.com>

RUN yum -y update
RUN yum -y install git vim
RUN yum -y install http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm
RUN yum -y install maven tomcat mysql mysql-devel mysql-server mysql-utilities
RUN yum install -y openssh-server

RUN useradd worker
RUN echo 'worker:worker' |chpasswd
RUN echo 'root:root' |chpasswd

RUN /sbin/service sshd start
RUN /sbin/service sshd stop

EXPOSE 8080
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
