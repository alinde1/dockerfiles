FROM centos:7.4.1708

COPY packages.txt /tmp/packages.txt
RUN yum -y --enablerepo=extras install epel-release && \
    yum -y --enablerepo=extras install $(cat /tmp/packages.txt)
