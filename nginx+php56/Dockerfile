FROM centos:7
MAINTAINER Jianfei Dan <dd@sinfere.com>

RUN yum -y update && yum clean all
RUN yum -y install --setopt=tsflags=nodocs epel-release && yum clean all

RUN rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
ADD remi.repo /etc/yum.repos.d/

RUN yum -y install php php-bcmath php-devel php-fpm php-gd php-json php-mbstring php-mcrypt php-opcache php-mysqlnd php-pdo

ADD nginx.repo /etc/yum.repos.d/
RUN yum -y install nginx

RUN yum -y install python-pip && pip install "pip>=1.4,<1.5" --upgrade
RUN pip install supervisor

ADD nginx.conf /etc/nginx
ADD php-fpm/www.conf /etc/php-fpm.d/
ADD supervisord.conf /etc/

EXPOSE 7001

CMD ["/usr/bin/supervisord"]
