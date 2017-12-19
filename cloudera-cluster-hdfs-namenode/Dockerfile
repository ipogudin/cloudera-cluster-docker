FROM ipogudin/cloudera-cluster-hadoop-node

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN mkdir -p /hdfs/nm

RUN yum -y install hadoop-hdfs-namenode && rm -rf /var/cache/yum/*

# configure not parametrized directories for format hdfs namenode
RUN dockerize -template "/usr/lib/hadoop/etc/templates/:/usr/lib/hadoop/etc/hadoop/"

RUN hdfs namenode -format

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 8020 50070

VOLUME /hdfs

CMD ["/usr/local/bin/dockerize", \
"-template", "/usr/lib/hadoop/etc/templates/:/usr/lib/hadoop/etc/hadoop/", \
"/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]