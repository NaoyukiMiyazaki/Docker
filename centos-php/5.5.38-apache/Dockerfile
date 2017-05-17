FROM centos:6.8
MAINTAINER minorut <taguchi@buddying.jp>

# Networking & Timezone
RUN echo "NETWORKING=yes" > /etc/sysconfig/network \
 && echo 'ZONE="Asia/Tokyo"' > /etc/sysconfig/clock

# Apache & PHP
RUN rpm -ivh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm \
 && rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm \
 && yum update -y \
 && yum install -y httpd \
 && yum install -y --enablerepo=remi-php55 \
        php \
        php-devel \
        php-dom \
        php-gd \
        php-intl \
        php-mbstring \
        php-mcrypt \
        php-mysqlnd \
        php-pdo \
        php-pecl-xdebug \
        php-pecl-apcu \
        php-posix \
        php-simplexml \
        php-soap \
        php-xml \
        php-xmlwriter \
        php-xsl \
 && yum install -y vim \
 && yum clean all \
 && chkconfig httpd on \
 && rm -rf /var/www/* \
 && mkdir /var/www/html

# Environment
ENV HOME=/root LANG=ja_JP.utf-8 DOCUMENT_ROOT=/var/www/html
WORKDIR $DOCUMENT_ROOT

CMD /usr/sbin/httpd -D FOREGROUND
EXPOSE 80