FROM ipogudin/cloudera-cluster-node

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN yum -y install hbase && \
rm -rf /var/cache/yum/*

RUN mkdir /etc/hbase/templates
COPY config-templates/* /etc/hbase/templates/

CMD ["hbase", "version"]