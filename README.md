# Keycloak for development

## Services:
1. [Keycloak](https://hub.docker.com/r/bitnami/keycloak)
2. [Postgres](https://hub.docker.com/r/bitnami/postgresql)
3. [Kafka](https://hub.docker.com/r/bitnami/kafka)
4. [Zookeeper](https://hub.docker.com/r/bitnami/zookeeper)
5. [PgAdmin](https://hub.docker.com/r/dpage/pgadmin4)
6. [KafkaUI](https://hub.docker.com/r/provectuslabs/kafka-ui)


## Exposed ports
- Keycloak: ```8181``` (HTTP)
- PG Admin: ```5050``` (HTTP)
- KafkaUI: ```2181``` (HTTP)


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
```shell
# run default consumer, for debug
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic topik.name.here
```
