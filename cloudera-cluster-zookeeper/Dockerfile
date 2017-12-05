FROM ipogudin/cloudera-cluster-node

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

VOLUME /var/lib/zookeeper

EXPOSE 2181 3881

CMD ["/usr/local/bin/dockerize", \
"-template", "/etc/zookeeper/templates/myid:/var/lib/zookeeper/myid", \
"-template", "/etc/zookeeper/templates/zoo.cfg:/etc/zookeeper/conf.dist/zoo.cfg", \
"-template", "/etc/zookeeper/templates/default-zookeeper:/etc/default/zookeeper", \
"/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]