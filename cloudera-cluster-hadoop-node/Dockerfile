FROM ipogudin/cloudera-cluster-node:5.14.2.1

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN yum -y install hadoop && \
rm -rf /var/cache/yum/*

RUN mkdir /usr/lib/hadoop/etc/templates
COPY config-templates/* /etc/hadoop/templates/

ENV HADOOP_HOME /usr/lib/hadoop
ENV HADOOP_CONF_DIR /etc/hadoop/conf
ENV HADOOP_COMMON_HOME /usr/lib/hadoop
ENV HADOOP_HDFS_HOME /usr/lib/hadoop-hdfs
ENV HADOOP_YARN_HOME /usr/lib/hadoop-yarn
ENV HADOOP_MAPRED_HOME /usr/lib/hadoop-mapreduce

CMD ["hadoop", "version"]
