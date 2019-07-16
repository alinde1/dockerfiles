FROM centos:7.4.1708

COPY packages.txt /tmp/packages.txt
RUN yum -y --enablerepo=extras install epel-release && \
    yum -y --enablerepo=extras install $(cat /tmp/packages.txt)

COPY requirements.txt /tmp/requirements.txt
RUN pip install --upgrade pip && \
    pip install setuptools==39.2.0 && \
    pip install -r /tmp/requirements.txt

RUN useradd -ms /bin/bash ansible
USER ansible
WORKDIR /home/ansible
COPY ansible_vault .ansible_vault
