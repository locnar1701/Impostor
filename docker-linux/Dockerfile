#
# Linux Dockerfile to build a working Impostor
# Server container based on CentOS 8
# Written and tested 25 October 2020
#
###################################################
#Base
FROM centos:8

#Upgrade to current and Install dependancies
RUN yum -y upgrade
RUN yum -y install libicu libicu-devel

# Imposter files in same folder as the Dockerfile
copy config.json /opt/impostor/config.json
copy Impostor.Server /opt/impostor/Impostor.Server
RUN chmod 755 /opt/impostor/Impostor.Server
RUN chmod 755 /opt/impostor/config.json

#Networking
EXPOSE 22023/udp

#Init
ENTRYPOINT ["/opt/impostor/Impostor.Server"]

#EOF
