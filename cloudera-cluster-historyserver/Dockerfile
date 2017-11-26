FROM ipogudin/cloudera-cluster-node

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 8032 8080

CMD ["/usr/local/bin/dockerize", \
"-template", "/usr/lib/hadoop/etc/templates/:/usr/lib/hadoop/etc/hadoop/", \
 "/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]