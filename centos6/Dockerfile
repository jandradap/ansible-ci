FROM centos:6.10

ARG BUILD_DATE
ARG VCS_REF
ARG VERSION
LABEL org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="ansible-ci" \
      org.label-schema.description="Image centos 6 with ansible for CI test" \
      org.label-schema.url="http://andradaprieto.es" \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.vcs-url="https://github.com/jandradap/ansible-ci" \
      org.label-schema.vendor="Jorge Andrada Prieto" \
      org.label-schema.version=$VERSION \
      org.label-schema.schema-version="1.0" \
      maintainer="Jorge Andrada Prieto <jandradap@gmail.com>" \
      org.label-schema.docker.cmd="docker run -i jorgeandrada/ansible-ci:centos6"

RUN yum install -y epel-release \
  && yum makecache fast \
  && yum install -y \
    libselinux-python \
    util-linux \
    selinux-policy \
    firewalld \
    jq \
    git \
    python2-pip \
    ca-certificates \
    sshpass \
    openssl \
  && pip install --upgrade \
    setuptools \
    pip \
    ansible \
    jmespath \
    jsonpath \
    jinja2 \
    PyYAML \
    paramiko \
    cryptography \
  && yum clean all \
  && mkdir /etc/ansible

COPY ansible.cfg /etc/ansible/
