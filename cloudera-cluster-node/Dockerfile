FROM centos:7.4.1708

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

ENV JDK_PACKAGE java-1.8.0-openjdk
ENV DOCKERIZE_VERSION v0.6.0
ENV CLOUDERA_VERSION 5.14.2 
ENV SPARK_PARCEL http://archive.cloudera.com/spark2/parcels/2.3.0.cloudera2/SPARK2-2.3.0.cloudera2-1.cdh5.13.3.p0.316101-el7.parcel

ADD common /opt/common

RUN yum -y install epel-release && rm -rf /var/cache/yum/*

RUN yum -y install wget supervisor $JDK_PACKAGE && rm -rf /var/cache/yum/*

RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && chown root:root /usr/local/bin/dockerize && chmod 555 /usr/local/bin/dockerize 

RUN wget https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/cloudera-cdh5.repo \
-O /etc/yum.repos.d/cloudera-cdh5.repo && \
sed -i "s#baseurl=https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/5/#baseurl=https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/${CLOUDERA_VERSION}/#g" /etc/yum.repos.d/cloudera-cdh5.repo

CMD ["bash", "-version"]
