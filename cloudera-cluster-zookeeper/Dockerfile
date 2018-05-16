FROM ipogudin/cloudera-cluster-node:5.14.2.1

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN yum -y install zookeeper && \
rm -rf /var/cache/yum/*

RUN mkdir /etc/zookeeper/templates
COPY config-templates/* /etc/zookeeper/templates/

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

VOLUME /var/lib/zookeeper

EXPOSE 2181 3881

CMD ["/usr/local/bin/dockerize", \
"-template", "/etc/zookeeper/templates/myid:/var/lib/zookeeper/myid", \
"-template", "/etc/zookeeper/templates/zoo.cfg:/etc/zookeeper/conf/zoo.cfg", \
"/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
