#FROM centos:centos7
FROM registry.access.redhat.com/ubi7/ubi

MAINTAINER Keith Ellis (keith.ellis@appdynamics.com)

# Install packages
#RUN yum install -y --disableplugin=subscription-manager https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
# RUN yum install -y --disableplugin=subscription-manager epel-release

#RUN yum install -y --disableplugin=subscription-manager libaio
RUN yum install -y --disableplugin=subscription-manager http://mirror.centos.org/centos/7/os/x86_64/Packages/libaio-0.3.109-13.el7.x86_64.rpm
RUN yum install -y --disableplugin=subscription-manager http://mirror.centos.org/centos/7/os/x86_64/Packages/libaio-devel-0.3.109-13.el7.x86_64.rpm
RUN yum install -y --disableplugin=subscription-manager net-tools
RUN yum install -y --disableplugin=subscription-manager http://mirror.centos.org/centos/7/os/x86_64/Packages/numactl-libs-2.0.12-5.el7.x86_64.rpm
RUN yum install -y --disableplugin=subscription-manager http://mirror.centos.org/centos/7/os/x86_64/Packages/numactl-2.0.12-5.el7.x86_64.rpm
RUN yum install -y --disableplugin=subscription-manager glibc

# Install EPEL repositories to get numactl

# Enable SSH
#RUN yum install -y openssh-server openssh-clients
#RUN chkconfig sshd on

# Install Oracle Java 7
#RUN wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie	" http://download.oracle.com/otn-pub/java/jdk/7u71-b14/jdk-7u71-linux-x64.rpm -O jdk-linux-x64.rpm
#RUN rpm -Uvh jdk-linux-x64.rpm
#RUN rm jdk-linux-x64.rpm
#ENV JAVA_HOME /usr/java/default
#ENV PATH $PATH:$JAVA_HOME/bin

# Add appdynamics user and set permissions
RUN groupadd -r -g 2002 appdynamics
RUN useradd --create-home --gid appdynamics -u 2001 appdynamics
RUN echo 'appdynamics:appdynamics' | chpasswd

