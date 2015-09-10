FROM centos:7

RUN rm -rf /etc/yum.repos.d/CentOS-Debuginfo.repo /etc/yum.repos.d/CentOS-Sources.repo /etc/yum.repos.d/CentOS-fasttrack.repo /etc/yum.repos.d/CentOS-CR.repo /etc/yum.repos.d/CentOS-Vault.repo
RUN sed -e 's|#baseurl=.*/centos/|baseurl=http://mirror.supremebytes.com/centos/|g;/mirrorlist=.*/d' /etc/yum.repos.d/CentOS-Base.repo -i

RUN yum clean all && \
  yum update -y --nogpg && \
  yum install -y epel-release && \
  yum install -y --nogpg rpm-build git python-setuptools yum-utils python2-devel intltool make python-pip gcc yum-plugin-priorities && \
  yum clean all

# Only added to speed up image builds
# TODO(derekh): Make this optional
RUN yum install -y --nogpg python-sqlalchemy python-webob python-eventlet ghostscript graphviz python-sphinx && \
  yum clean all
