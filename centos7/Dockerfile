FROM centos:7

ARG BUILD_DATE
ARG VCS_REF
ARG VERSION
LABEL org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="ansible-ci" \
      org.label-schema.description="Image centos 7 with ansible for CI test" \
      org.label-schema.url="http://andradaprieto.es" \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.vcs-url="https://github.com/jandradap/ansible-ci" \
      org.label-schema.vendor="Jorge Andrada Prieto" \
      org.label-schema.version=$VERSION \
      org.label-schema.schema-version="1.0" \
      maintainer="Jorge Andrada Prieto <jandradap@gmail.com>" \
      org.label-schema.docker.cmd="docker run -i jorgeandrada/ansible-ci:centos7"

RUN yum install -y epel-release \
  && yum makecache fast \
  && yum install -y ansible \
  libselinux-python \
  util-linux \
  selinux-policy \
  firewalld \
  jq \
  git \
  && yum clean all
