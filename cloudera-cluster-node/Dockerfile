FROM ipogudin/cloudera-cluster-base-oracle-jdk8

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

ENV CLOUDERA_VERSION 5.13.0 

RUN wget https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/cloudera-cdh5.repo \
-O /etc/yum.repos.d/cloudera-cdh5.repo && \
sed -i "s#baseurl=https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/5/#baseurl=https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/${CLOUDERA_VERSION}/#g" /etc/yum.repos.d/cloudera-cdh5.repo && \
yum -y install hadoop && \
rm -rf /var/cache/yum/*

RUN mkdir /usr/lib/hadoop/etc/templates

COPY config/* /usr/lib/hadoop/etc/templates/

#COPY config/* /usr/lib/hadoop/etc/hadoop/

ENV HADOOP_HOME /usr/lib/hadoop
ENV HADOOP_CONF_DIR /etc/hadoop/conf
ENV HADOOP_COMMON_HOME /usr/lib/hadoop
ENV HADOOP_HDFS_HOME /usr/lib/hadoop-hdfs
ENV HADOOP_YARN_HOME /usr/lib/hadoop-yarn
ENV HADOOP_MAPRED_HOME /usr/lib/hadoop-mapreduce

CMD ["hadoop", "version"]