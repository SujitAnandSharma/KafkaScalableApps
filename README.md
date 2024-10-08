# KafkaScalableApps

/************************
                Setting up Kafka Cluster
*************************************/

1. Please make sure that Docker is already installed in the system,
If not, install from https://www.docker.com/products/docker-desktop

2. If on Windows O/S, open a Powershell window.
If on Mac OS or Linux, open a Terminal window.

3. Navigate to the directory where the exercise files are downloaded.
This directory would contain the kafka-single-node.yml file

4. Execute the following command from this directory

        docker-compose -f kafka-cluster.yml up -d

5. Check if the containers are up and running

        docker ps


6. To shutdown and remove the setup, execute this command in the same directory

        docker-compose -f kafka-cluster.yml down

/*******************************
                Creating Topics
***************************/

1. Create a topic "kafka.learning.orders" with 3 partitions and 2 replicas

2. Create a topic "kafka.learning.tweets" with 4 partitions and 3 replicas

/********************************
                Resiliency in Action
*******************************/

1. Login to kafka-3 using
        docker exec -it kafka-3 /bin/bash

2. Look at current controller status using

    ./kafka-metadata-quorum.sh \
            --bootstrap-server localhost:19094 \
            describe --status

3. Stop a broker by using

    docker container stop <broker-name>

4. Start a broker by using

    docker container start <broker-name>



/********************
               Thanks for following
*************************/

