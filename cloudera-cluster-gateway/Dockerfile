FROM ipogudin/cloudera-cluster-node

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN yum -y install pig hive spark-worker && rm -rf /var/cache/yum/*

RUN mkdir /data-dir

VOLUME /data-dir

# configure not parametrized directories for format hdfs namenode
RUN dockerize -template "/usr/lib/hadoop/etc/templates/:/usr/lib/hadoop/etc/hadoop/"

CMD ["/usr/local/bin/dockerize", \
"-template", "/usr/lib/hadoop/etc/templates/:/usr/lib/hadoop/etc/hadoop/", \
"/bin/bash"]