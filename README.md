docker network create cloudera-cluster-net

docker run --rm -i -t ipogudin/cloudera-cluster-hdfs-namenode bash

docker exec -i -t CONTAINER_ID bash

##
docker exec -i -t gateway hdfs dfs -ls /

docker run --rm -i -t --network cloudera-cluster-net ipogudin/cloudera-cluster-gateway hdfs dfs -ls /


# Useful links
- [Installing and Deploying CDH Using the Command Line](https://www.cloudera.com/documentation/enterprise/latest/topics/cdh_ig_command_line.html)