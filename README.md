
https://medium.com/big-data-engineering/hello-kafka-world-the-complete-guide-to-kafka-with-docker-and-python-f788e2588cfc
#### kafka-docker 
git clone https://github.com/wurstmeister/kafka-docker.git 
cd kafka-docker

#### Update KAFKA_ADVERTISED_HOST_NAME inside 'docker-compose.yml',  
docker-compose up -d

#### You can check the proceses running with:
docker-compose ps

#### Destroy the cluster when you are done with it
docker-compose stop

#### inside 
docker exec -it conatainerId /bin/sh
cd /opt/kafka

#### del port 
sudo lsof -i :9092
sudo kill -9 PID


#### del docker
docker stop $(docker ps -aq)    
docker rm $(docker ps -aq)    
docker rmi $(docker images -q)