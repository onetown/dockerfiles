FROM centos 

MAINTAINER The CentOS Project <cloud-ops@centos.org>
LABEL Vendor="trystack"
LABEL License=GPLv2
LABEL Version=5.5.41


RUN  yum -y install --setopt=tsflags=nodocs mariadb-server bind-utils pwgen psmisc hostname && \ 
    yum -y erase vim-minimal && \
    yum -y update && yum clean all

VOLUME /var/lib/mysql

COPY docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

EXPOSE 3306
CMD ["mysqld_safe"]

