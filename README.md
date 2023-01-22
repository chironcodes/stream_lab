# stream_lab




docker exec -i -t -u root $(docker ps | grep kafka | cut -d' ' -f1) /bin/bash


#create a new topic
kafka-topics.sh --create --partitions 4 --bootstrap-server kafka:9092 --topic dns_topq

#lists all topics
kafka-topics.sh --bootstrap-server kafka:9092 --list

#starts a produces on topic
kafka-console-producer.sh --broker-list kafka:9092 --topic=dns_topq

#consumes topic
kafka-console-consumer.sh --from-beginning --bootstrap-server kafka:9092 --topic=dns_topq