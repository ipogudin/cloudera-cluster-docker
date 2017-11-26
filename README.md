
docker run --rm -i -t ipogudin/cloudera-cluster-hdfs-namenode bash

docker exec -i -t CONTAINER_ID bash

docker run --rm -i -t --network clouderaclusterdocker_default ipogudin/cloudera-cluster-gateway hdfs dfs -ls /