FROM ipogudin/cloudera-cluster-datanode:5.14.2.1

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

RUN mkdir /shared

RUN mkdir /etc/hbase/templates
COPY config-templates/* /etc/hbase/templates/

RUN mkdir /etc/spark2/conf && \
ln -s /etc/hadoop/conf /etc/spark2/conf/yarn-conf

RUN mkdir /etc/spark/templates
COPY spark-config-templates/* /etc/spark/templates/

RUN mkdir /etc/spark2/templates
COPY spark2-config-templates/* /etc/spark2/templates/

RUN bash /etc/spark2/templates/classpath-generator > /etc/spark2/conf/classpath.txt

ADD gateway /bin/gateway
RUN chmod 555 /bin/gateway

CMD ["/usr/local/bin/dockerize", \
"-template", "/etc/hadoop/templates/:/etc/hadoop/conf/", \
"-template", "/etc/hbase/templates/:/etc/hbase/conf/", \
"-template", "/etc/spark/templates/spark-defaults.conf:/etc/spark/conf/spark-defaults.conf", \
"-template", "/etc/spark/templates/log4j.properties:/etc/spark/conf/log4j.properties ", \
"-template", "/etc/spark2/templates/:/etc/spark2/conf/", \
"/bin/gateway"]
