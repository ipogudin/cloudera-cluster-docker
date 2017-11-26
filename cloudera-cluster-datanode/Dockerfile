FROM ipogudin/cloudera-cluster-node

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN mkdir -p /hdfs/data

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 50020 50075 8042

VOLUME /hdfs

CMD ["/usr/local/bin/dockerize", \
"-template", "/usr/lib/hadoop/etc/templates/:/usr/lib/hadoop/etc/hadoop/", \
"/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]