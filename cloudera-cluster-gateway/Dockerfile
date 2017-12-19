FROM ipogudin/cloudera-cluster-hadoop-node

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN yum -y install pig hive spark-worker hbase && rm -rf /var/cache/yum/*

RUN mkdir /shared

RUN mkdir /etc/hbase/templates
COPY config-templates/* /etc/hbase/templates/

CMD ["/usr/local/bin/dockerize", \
"-template", "/usr/lib/hadoop/etc/templates/:/usr/lib/hadoop/etc/hadoop/", \
"-template", "/etc/hbase/templates/:/etc/hbase/conf/", \
"/bin/sleep", "365000d"]