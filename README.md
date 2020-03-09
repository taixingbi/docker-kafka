

#### kafka-docker 
git clone https://github.com/wurstmeister/kafka-docker.git 
cd kafka-docker

#### Update KAFKA_ADVERTISED_HOST_NAME inside 'docker-compose.yml',  
docker-compose up -d

#### Optional - Scale the cluster by adding more brokers (Will start a single zookeeper instance)
docker-compose scale kafka=3

#### You can check the proceses running with:
docker-compose ps

#### Destroy the cluster when you are done with it
docker-compose stop

#### inside 
docker exec -it conatainerId /bin/sh
cd /opt/kafka

bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic test
bin/kafka-topics.sh --list --bootstrap-server localhost:9092

bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 3 --partitions 1 --topic test
bin/kafka-topics.sh --describe --bootstrap-server localhost:9092 --topic test

#### del docker
docker stop $(docker ps -aq)    
docker rm $(docker ps -aq)    
docker rmi $(docker images -q)

