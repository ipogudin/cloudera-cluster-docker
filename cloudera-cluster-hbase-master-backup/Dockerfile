FROM ipogudin/cloudera-cluster-hbase-node:5.13.0.1

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

CMD ["/usr/local/bin/dockerize", \
"-template", "/etc/hbase/templates/:/etc/hbase/conf/", \
 "/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
