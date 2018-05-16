FROM ipogudin/cloudera-cluster-hadoop-node:5.14.2.1

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN mkdir -p /hdfs/nm

RUN yum -y install hadoop-hdfs-namenode && rm -rf /var/cache/yum/*

# configure not parametrized directories for format hdfs namenode
RUN dockerize -template "/etc/hadoop/templates/:/etc/hadoop/conf/"

RUN hdfs namenode -format

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 8020 50070

VOLUME /hdfs

CMD ["/usr/local/bin/dockerize", \
"-template", "/etc/hadoop/templates/:/etc/hadoop/conf/", \
"/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
