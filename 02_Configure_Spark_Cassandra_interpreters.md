## Configure Zeppelin Interpreters for Apache Spark & Apache Cassandra

#### go to ` http://<ZEPPELIN_SERVER_IP>:9990/next/#/interpreter `

---

##### minimum properties/settings for Apache Spark Interpreter

| Name  | Value |
| ------------- | ------------- |
| spark.master | spark://<SPARK_MASTER_IP>:7077 |
| spark.jars | /apps/opt/cassandra/spark-cassandra-connector-jars/spark-cassandra-connector.jar |
| zeppelin.spark.enableSupportedVersionCheck | false |

---

##### minimum properties/settings for Apache Cassandra Interpreter

| Name  | Value |
| ------------- | ------------- |
| cassandra.hosts | <CASS_IPS_COMMA_SEPARATED> |
| cassandra.cluster | <CLUSER_NAME> |
| cassandra.credentials.username | <USER> |
| cassandra.credentials.password | <PASSWORD> |

---

