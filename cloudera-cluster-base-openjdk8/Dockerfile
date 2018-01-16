FROM centos:7.4.1708

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

ENV JDK_PACKAGE java-1.8.0-openjdk-1.8.0.151
ENV DOCKERIZE_VERSION v0.6.0

RUN yum -y install epel-release && rm -rf /var/cache/yum/*

RUN yum -y install wget supervisor $JDK_PACKAGE && rm -rf /var/cache/yum/*

RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && chown root:root /usr/local/bin/dockerize && chmod 555 /usr/local/bin/dockerize 

CMD ["java", "-version"]