## Install & Configure Apache Zeppelin

#### go to ` http://zeppelin.apache.org/download.html `
#### download ` zeppelin-<VERSION>-bin-all.tgz `

---

##### at the time of writing this document

` Apache Zeppelin version 0.9.0 ` was released on ` 26th December 2020 `

Binary package ` zeppelin-0.9.0-bin-all.tgz ` of size ` 1.5g ` was available for download.

---

##### during this install :

we will use ` CentOS Linux ` server <br>
Zeppelin will run under ` cassandra ` user <br>
` ~ = /apps/opt/cassandra `

---

#### extract binary package and create folders

```
cd ~
tar -xvf zeppelin-0.9.0-bin-all.tgz

ln -s ~/zeppelin-0.9.0-bin-all ~/zeppelin-current

mkdir ~/zeppelin-current/logFiles
mkdir ~/zeppelin-current/tempWorkSpace
mkdir ~/zeppelin-current/savedNotebooks

chmod -R o-rwx ~/zeppelin-current
```

#### configuration
```
cp ~/zeppelin-current/conf/zeppelin-env.sh.template ~/zeppelin-current/conf/zeppelin-env.sh
```

#### most or all entries in this file should be already commented out
```
grep -v "#" ~/zeppelin-current/conf/zeppelin-env.sh
```

#### add following entries to ` ~/zeppelin-current/conf/zeppelin-env.sh `
```
export ZEPPELIN_HOME=~/zeppelin-current
export ZEPPELIN_ADDR=`hostname`
export ZEPPELIN_PORT=9990
export ZEPPELIN_LOG_DIR=${ZEPPELIN_HOME}/logFiles
export ZEPPELIN_PID_DIR=${ZEPPELIN_HOME}/logFiles
export ZEPPELIN_WAR_TEMPDIR=${ZEPPELIN_HOME}/tempWorkSpace
export ZEPPELIN_NOTEBOOK_DIR=${ZEPPELIN_HOME}/savedNotebooks
export ZEPPELIN_IDENT_STRING=zeppelin_user
```

#### set file permissions ` ~/zeppelin-current/conf/zeppelin-env.sh `
```
chmod ug+x ~/zeppelin-current/conf/zeppelin-env.sh
```

---

#### start and stop Apache Zeppelin

```
~/zeppelin-current/bin/zeppelin-daemon.sh start
```

```
~/zeppelin-current/bin/zeppelin-daemon.sh stop
```

#### log files :
```
~/zeppelin-current/logFiles/*
```

---

#### Apache Zeppelin Web Interface :

```
http://<ZEPPELIN_SERVER_IP>:9990/next
```
