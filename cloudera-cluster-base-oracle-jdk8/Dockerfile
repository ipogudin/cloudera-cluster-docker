FROM centos:7.4.1708

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

ENV JDK_RPM jdk-8u151-linux-x64.rpm
ENV DOCKERIZE_VERSION v0.6.0

RUN yum -y install epel-release && rm -rf /var/cache/yum/*

RUN yum -y install wget supervisor &&  rm -rf /var/cache/yum/*

RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && chown root:root /usr/local/bin/dockerize && chmod 555 /usr/local/bin/dockerize 

RUN wget --header "Cookie: oraclelicense=accept-securebackup-cookie" \
    http://download.oracle.com/otn-pub/java/jdk/8u151-b12/e758a0de34e24606bca991d704f6dcbf/${JDK_RPM} \
    -O /tmp/${JDK_RPM} && yum -y install /tmp/${JDK_RPM} \
    && rm /tmp/${JDK_RPM} &&  rm -rf /var/cache/yum/*

CMD ["java", "-version"]