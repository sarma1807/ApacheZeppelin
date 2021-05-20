## My_First_Notebook : Apache Zeppelin Notebook
---
```
%cassandra
select broadcast_address, cluster_name from system.local ;
```
---
```
%cassandra
select peer from system.peers ;
```
---
```
%spark
sc.version
```
---
```
%spark
import org.apache.spark.SparkContext
import org.apache.spark.SparkConf
import com.datastax.spark.connector._
import com.datastax.spark.connector.cql.CassandraConnector
import org.apache.spark.sql.cassandra._
import org.apache.spark.sql.{Dataset, SaveMode}
import sys.process._
spark.conf.set("spark.sql.catalog.cass_db_1", "com.datastax.spark.connector.datasource.CassandraCatalog")
spark.conf.set("spark.sql.defaultCatalog", "cass_db_1")
spark.conf.set("spark.sql.catalog.cass_db_1.spark.cassandra.connection.host", "192.168.1.171,192.168.1.172")
spark.conf.set("spark.sql.catalog.cass_db_1.spark.cassandra.auth.username", "thor")
spark.conf.set("spark.sql.catalog.cass_db_1.spark.cassandra.auth.password", "oracle")
// spark.sparkContext.listJars.foreach(println)
// spark.conf.getAll.foreach(println)
"date".!

spark.sql("SELECT * FROM sales.daily_sales").show(10, false)
```
---
```
%cassandra
SELECT * FROM sales.daily_sales ;
```
---
