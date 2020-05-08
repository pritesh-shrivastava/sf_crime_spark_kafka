### Directions

Start Zookeeper & Kafka Server on 2 separate terminals :

```
/usr/bin/zookeeper-server-start config/zookeeper.properties

/usr/bin/kafka-server-start config/server.properties
```


To insert data into the topic, run :
```
python kafka_server.py
```

To start the Kafka consumer, run :
```
kafka-console-consumer --topic calls --from-beginning --bootstrap-server localhost:9092
```

To submit the Spark job, run :
```
spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.4 --master local[*] --conf spark.ui.port=3000 data_stream.py
```