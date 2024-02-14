# Keycloak for development

1. Clone this repository for local development.
2. Create ```.env``` file or rename ```.env.example```
3. Run with comand: ```docker compose up -d```


## Services:
1. [Keycloak](https://hub.docker.com/r/bitnami/keycloak)
2. [Postgres](https://hub.docker.com/r/bitnami/postgresql)
3. [Kafka](https://hub.docker.com/r/bitnami/kafka)
4. [Zookeeper](https://hub.docker.com/r/bitnami/zookeeper)
5. [PgAdmin](https://hub.docker.com/r/dpage/pgadmin4)
6. [KafkaUI](https://hub.docker.com/r/provectuslabs/kafka-ui)


## Exposed ports
- Keycloak: ```8181``` [link](http://localhost:8181)
- PG Admin: ```5050``` [link](http://localhost:5050)
- KafkaUI: ```2181``` [link](http://localhost:2181)


## Custom theme and SPI
Copy your SPI to ```./providers``` and themes to ```./themes```


## Default credentials

### Keycloak
```text
username: user     // env: KEYCLOAK_ADMIN_USER
password: bitnami  // env: KEYCLOAK_ADMIN_PASSWORD
```

### Postgres
```text
username from env: DB_USER
password from env: DB_PASSWORD
database name from env: DB_NAME
```

### PG Admin
```text
username from env: PGADMIN_USER, must be email
password from env: PGADMIN_PASSWORD
```

### Kafka:
Create topic with 3 partitions and replication factor equals 1
```shell
# run in kafka container instance
kafka-topics.sh --bootstrap-server kafka:9092 --create --if-not-exists --topic <topik.name.here> --replication-factor 1 --partitions 3
```

Consumer for debugging
```shell
# run in kafka container instance
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic topik.name.here
```

> **_NOTE:_**  Replace the <topik.name.here> with your topic name
