# Vagrant Kafka

## Setup

1. install [vagrant](https://www.vagrantup.com/docs/installation/)
1. Clone this repo
1. Run `vagrant up` in the repo (will install needed resources)
1. Run `vagrant ssh` to login into the virtual machine
1. Run `startkafka` (will start the kafka server on the virtual machine)

### Notes

- Kafka is on local virtual machine ip `192.168.33.10`

## Check Kafka

### Create a new topic

```
bin/kafka-topics.sh --create --zookeeper 192.168.33.10:2181 --replication-factor 1 --partitions 1 --topic test
```

### Init a Producer

```
bin/kafka-console-producer.sh --broker-list 192.168.33.10:9092 --topic test
```

### Init a Consumer

```
bin/kafka-console-consumer.sh --bootstrap-server 192.168.33.10:9092 --topic test --from-beginning
```

## Useful Actions

### Delete a topic

Will delete a topic and it's message history

```
bin/kafka-topics.sh --zookeeper 192.168.33.10:2181 --delete --topic test
```
