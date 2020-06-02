#FROM centos:centos7
FROM registry.access.redhat.com/ubi7/ubi

MAINTAINER Keith Ellis (keith.ellis@appdynamics.com)

#RUN groupadd -r -g 2002 appdynamics
#RUN useradd --create-home --gid appdynamics -u 2001 appdynamics
#RUN echo 'appdynamics:appdynamics' | chpasswd

# Install packages
#RUN yum install -y --disableplugin=subscription-manager libaio

RUN mkdir -p /sharedFiles
#RUN chown appdynamics:appdynamics /sharedFiles

# COPY --chown=appdynamics:appdynamics platform-setup-x64-linux-20.3.5.21927.sh /sharedFiles/platform-setup.sh

COPY platform-setup-x64-linux-20.3.5.21927.sh /sharedFiles/platform-setup.sh
RUN chmod +x /sharedFiles/platform-setup.sh

#USER appdynamics

CMD ["tail", "-f", "/dev/null"]
