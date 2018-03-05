FROM ipogudin/cloudera-cluster-hadoop-node:5.13.0.1

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 8032 8080

CMD ["/usr/local/bin/dockerize", \
"-template", "/etc/hadoop/templates/:/etc/hadoop/conf/", \
 "/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
