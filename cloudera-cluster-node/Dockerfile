FROM ipogudin/cloudera-cluster-base-oracle-jdk8

MAINTAINER Ivan Pogudin <i.a.pogudin@gmail.com>

ENV CLOUDERA_VERSION 5.13.0 

RUN wget https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/cloudera-cdh5.repo \
-O /etc/yum.repos.d/cloudera-cdh5.repo && \
sed -i "s#baseurl=https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/5/#baseurl=https://archive.cloudera.com/cdh5/redhat/7/x86_64/cdh/${CLOUDERA_VERSION}/#g" /etc/yum.repos.d/cloudera-cdh5.repo

CMD ["bash", "-version"]