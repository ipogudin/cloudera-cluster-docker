FROM ipogudin/cloudera-cluster-hdfs-namenode

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 8020 50090

VOLUME /hdfs

CMD ["/usr/local/bin/dockerize", \
"-template", "/usr/lib/hadoop/etc/templates/:/usr/lib/hadoop/etc/hadoop/", \
"/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]