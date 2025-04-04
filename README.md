# Reference: 
- [Youtube](https://www.youtube.com/watch?v=Ydts27Qa8H0)
- [Github](https://github.com/darshilparmar/kafka-in-10min-video-code/blob/main/commands.sh)

### Step 1
- Create a docker-compose.yaml file based on the [file](docker-compose.yaml)
- Run the ``` docker-compose up ``` command

### Step 2
- Open a new terminal and run the ``` docker ps ``` command
- This will list all the containers

### Step 3
- Run the ``` docker exec -it <kafka_container_id> /bin/bash ``` command
- This will connect to the kafka container

### Step 4
- Once inside the container, run the ``` cd /opt/kafka/bin ``` command
- This will change the directory to /opt/kafka/bin

### Step 5
- Run the ``` ./kafka-topics.sh --create --topic test-topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 ``` command
- This will create a new topic with name test-topic with replication factor 1 and 1 partition

### Step 6
- Run the ``` ./kafka-console-producer.sh --topic test-topic --bootstrap-server localhost:9092 ``` command
- This will start the kafka producer

### Step 7
- Now open a new terminal and run the ``` docker ps ``` command to get the kafka container id
- Then run the ``` docker exec -it <kafka_container_id> /bin/bash ``` command to connect to the container
- Once inside the container, run the ``` cd /opt/kafka/bin ``` command
- Now run the ``` ./kafka-console-consumer.sh --topic test-topic --bootstrap-server localhost:9092 --from-beginning ``` command
- This will start the kafka consumer

