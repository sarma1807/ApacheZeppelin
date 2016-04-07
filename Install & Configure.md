##### Make a copy of `conf/zeppelin-env.sh.template` as `conf/zeppelin-env.sh`

`cp $ZEPPELIN_HOME/conf/zeppelin-env.sh.template $ZEPPELIN_HOME/conf/zeppelin-env.sh`

---

##### Modify `$ZEPPELIN_HOME/conf/zeppelin-env.sh` and configure following parameters :

```

############### MY ZEPPELIN SETTINGS - START ##############################

##### ZEPPELIN SETTINGS #####
export ZEPPELIN_PORT=9990
export ZEPPELIN_LOG_DIR=/u01/cass/zeppelin-0.5.6/logFiles
export ZEPPELIN_PID_DIR=/u01/cass/zeppelin-0.5.6/logFiles        # zeppelin process id saved to this folder in a file called 
export ZEPPELIN_WAR_TEMPDIR=/u01/cass/zeppelin-0.5.6/tempWorkSpace       # The location of jetty temporary directory
export ZEPPELIN_NOTEBOOK_DIR=/u01/cass/zeppelin-0.5.6/savedNotebooks
export ZEPPELIN_IDENT_STRING=zeppelin_user    # A string representing this instance of zeppelin. $USER by default.

##### SPARK SETTINGS #####
export MASTER=spark://<SPARK_MASTER_IP:PORT>      # spark master URL
export SPARK_HOME=$SPARK_HOME
# export SPARK_HOME=/u01/cass/spark-1.6.0-bin-hadoop2.6
# export SPARK_SUBMIT_OPTIONS                 # (optional) extra options to pass to spark submit. eg) "--driver-memory 512M --executor-memory 1G".

##### PYSPARK SETTINGS #####
# export PYSPARK_PYTHON                       # path to the python command. must be the same path on the driver(Zeppelin) and all workers.
# export PYTHONPATH

##### SPARK ADVANCED SETTINGS #####
export ZEPPELIN_SPARK_USEHIVECONTEXT=false    # Use HiveContext instead of SQLContext if set true. true by default.
# export ZEPPELIN_SPARK_CONCURRENTSQL         # Execute multiple SQL concurrently if set true. false by default.
# export ZEPPELIN_SPARK_MAXRESULT             # Max number of SparkSQL result to display. 1000 by default.

############### MY ZEPPELIN SETTINGS - END ################################

```

---

##### Make ` $ZEPPELIN_HOME/conf/zeppelin-env.sh ` file executable :

``` chmod ugo+x $ZEPPELIN_HOME/conf/zeppelin-env.sh ```

---

##### Start / Stop Apache Zeppelin :

``` $ZEPPELIN_HOME/bin/zeppelin-daemon.sh [ start | stop ] ```

---

##### Apache Zeppelin Notebook :

``` http://<ZEPPELIN_SERVER_IP>:9990/ ```

---
