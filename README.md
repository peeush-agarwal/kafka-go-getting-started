# Tutorial on Apache Kafka using Golang

[Apache Kafka](https://kafka.apache.org/) is an open-source event streaming platform, used for publishin and processing events at high-throughput.

## Running Kafka cluster in local machine

```shell
docker-compose up -d
```

### Create a topic in the Kafka broker

```shell
docker compose exec broker kafka-topics --create --topic purchases --boostrap-server localhost:9092 --replication-factor 1 --partitions 1
```

## Build Producer

```shell
go build -o out/producer util.go producer.go
```

### Run Producer

```shell
./out/producer getting-started.properties
```

## Build Consumer

```shell
go build -o out/consumer util.go consumer.go
```

### Run Consumer

```shell
./out/consumer getting-started.properties
```

_Enter `Ctrl+C` to exit_
