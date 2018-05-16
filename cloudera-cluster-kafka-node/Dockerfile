FROM ipogudin/cloudera-cluster-node:5.14.2.1

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

ENV CLOUDERA_KAFKA_VERSION 3.0.0 

RUN wget http://archive.cloudera.com/kafka/redhat/7/x86_64/kafka/cloudera-kafka.repo \
-O /etc/yum.repos.d/cloudera-kafka.repo && \
sed -i "s#baseurl=http://archive.cloudera.com/kafka/redhat/7/x86_64/kafka/1/#baseurl=http://archive.cloudera.com/kafka/redhat/7/x86_64/kafka/${CLOUDERA_KAFKA_VERSION}/#g" /etc/yum.repos.d/cloudera-kafka.repo

RUN yum -y install kafka && \
rm -rf /var/cache/yum/*

RUN mkdir /etc/kafka/templates
COPY config-templates/* /etc/kafka/templates/

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

VOLUME /var/lib/kafka

CMD ["/usr/local/bin/dockerize", \
"-template", "/etc/kafka/templates/:/etc/kafka/conf/", \
"/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
