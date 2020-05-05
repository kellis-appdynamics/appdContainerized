#FROM centos:centos7
FROM registry.access.redhat.com/ubi7/ubi

MAINTAINER Keith Ellis (keith.ellis@appdynamics.com)

# Install packages
#RUN yum install -y --disableplugin=subscription-manager libaio

RUN mkdir -p /sharedFiles

COPY platform-setup-x64-linux-20.3.5.21927.sh /sharedFiles/platform-setup.sh

CMD ["tail", "-f", "/dev/null"]
