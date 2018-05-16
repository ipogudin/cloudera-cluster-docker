FROM ipogudin/cloudera-cluster-hadoop-node:5.14.2.1

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN mkdir -p /hdfs/data

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 50020 50075 8042

VOLUME /hdfs

RUN bash /opt/common/spark2-installer

RUN yum -y install pig hive spark-worker hbase && rm -rf /var/cache/yum/*

CMD ["/usr/local/bin/dockerize", \
"-template", "/etc/hadoop/templates/:/etc/hadoop/conf/", \
"/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
