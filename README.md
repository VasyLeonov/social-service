# Social-service

Бэкенд социальной сети java spring boot.

# Стек технологий 

- REST API
- WebSocket
- MapStruct
- Kafka
- JwtToken
- JPA Specifications
- Liquibase
- Swagger

Tests:
- JUnit5
- EmbeddedKafka
- EmbeddedPostgres
- Mockito

# Запуск локально в intellij idea с Docker

Postgres:
- docker run -p 5432:5432 --name postgres -e POSTGRES_PASSWORD=postgres -d postgres

Frontend:
- docker run -p 8097:80 -name frontend team33/front-for-local:1.1

Kafka:
- docker network create kafkanet

- docker run -d --network=kafkanet --name=zookeeper -e ZOOKEEPER_CLIENT_PORT=2181 -e ZOOKEEPER_TICK_TIME=2000 -p 2181:2181 wurstmeister/zookeeper:latest

- docker run -d --network=kafkanet --name=kafka -e KAFKA_ZOOKEEPER_CONNECT=zookeeper:2181 -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://localhost:9092 -e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 -p 9092:9092 confluentinc/cp-kafka:latest  
