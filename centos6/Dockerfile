FROM centos:6.9
RUN rpm -ivh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm \
  && yum install -y centos-release-scl libffi \
  && yum install -y python27 \
  && scl enable python27 bash \
  && yum install -y python-pip pyopenssl ndg-httpsclient pyasn1 \
  && pip install --upgrade pip \
  && pip install setuptools \
  && pip install ansible \
  && yum install -y openssh-server ca-certificates \
  && yum clean all
