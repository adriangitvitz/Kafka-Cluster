## KAFKA CLUSTER

The reason why I develop this, is because i did not find proper documentation on how to integrate this services for kafka. <br>

> This project includes the following:
* Zookeeper
* Kafka Brokers (2)
* Postgresql
* Schema-Registry
* Ksql Server
* Kafka Connect
* Grafana
* JMX Prometheus Exporter (2)

The brokers are using SASL_PLAINTEXT externally and PLAINTEXT locally

> How to run
``` shell
docker-compose up -d
```

> Get current data from kafka

``` shell
docker run -it --network=host edenhill/kcat:1.7.1 -b localhost:9092 -X security.protocol=SASL_PLAINTEXT -X sasl.mechanism=PLAIN -X sasl.username=admin -X sasl.password=admin-secret -L
```

### NOTE: Change the values in the .env file according to your needs

References:
* Metrics with Prometheus: https://github.com/streamthoughts/kafka-monitoring-stack-docker-compose
