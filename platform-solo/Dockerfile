#FROM centos:centos7
FROM registry.access.redhat.com/ubi7/ubi

MAINTAINER Keith Ellis (keith.ellis@appdynamics.com)

# Add appdynamics user and set permissions
RUN groupadd -r -g 2002 appdynamics
RUN useradd --create-home --gid appdynamics -u 2001 appdynamics
RUN echo 'appdynamics:appdynamics' | chpasswd

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

RUN yum install -y --disableplugin=subscription-manager openssh-clients
RUN yum install -y --disableplugin=subscription-manager openssh

# Install EPEL repositories to get numactl

# Copy over the necessary scripts
#COPY --chown=appdynamics:appdynamics docker-entrypoint.sh /scripts/docker-entrypoint.sh
#COPY --chown=appdynamics:appdynamics response.varfile /scripts/response.varfile

COPY docker-entrypoint.sh /scripts/docker-entrypoint.sh
COPY response.varfile /scripts/response.varfile

# USER appdynamics
#ENTRYPOINT ["/scripts/docker-entrypoint.sh"]

CMD tail -f /dev/null
