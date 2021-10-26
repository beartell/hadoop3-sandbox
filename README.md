# Hadoop v3 - Docker Sandbox

### 1. Docker Üzerinden Imaj Dosyası İndirilir <h2>
    $ docker pull xentnex/hadoop:v3.0.0
### 2. Docker Imajı Çalıştırılır. <h2> 
    $ docker run -td <image_id>
### 3. Çalıştırılan Imaj'ın Container'ina Terminal Bağlantısı Sağlanır. <h2> 
    $ docker exec -ti <container_id> /bin/bash
### 4. Imaj'ın İçinde Bulunan Hadoop Ekosistemine Ait Yazılımlar Çalıştırılabilir. <h2> 
#### 4.1 HBase
    $ hbase version
    OpenJDK 64-Bit Server VM warning: Using incremental CMS is deprecated and will likely be removed in a future release
    SLF4J: Class path contains multiple SLF4J bindings.
    SLF4J: Found binding in [jar:file:/usr/lib/hadoop/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
    SLF4J: Found binding in [jar:file:/usr/lib/hbase/lib/client-facing-thirdparty/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
    SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
    SLF4J: Actual binding is of type [org.slf4j.impl.Log4jLoggerFactory]
    HBase 2.2.6
    Source code repository file:///ws/output/hbase/hbase-2.2.6 revision=Unknown
    Compiled by jenkins on Sun Oct 17 01:52:13 UTC 2021
    From source with checksum a590ebb32ebb0937ddc7287f7c1b0f80
    
    $ hbase shell
    OpenJDK 64-Bit Server VM warning: Using incremental CMS is deprecated and will likely be removed in a future release
    SLF4J: Class path contains multiple SLF4J bindings.
    SLF4J: Found binding in [jar:file:/usr/lib/hadoop/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
    SLF4J: Found binding in [jar:file:/usr/lib/hbase/lib/client-facing-thirdparty/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
    SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
    SLF4J: Actual binding is of type [org.slf4j.impl.Log4jLoggerFactory]
    HBase Shell
    Use "help" to get list of supported commands.
    Use "exit" to quit this interactive shell.
    For Reference, please visit: http://hbase.apache.org/2.0/book.html#shell
    Version 2.2.6, rUnknown, Sun Oct 17 01:52:13 UTC 2021
    Took 0.0020 seconds
    hbase(main):001:0>
  
#### 4.2 HDFS
    $ hdfs version
    Hadoop 3.2.2
    Source code repository https://gitbox.apache.org/repos/asf/bigtop.git -r 09d20bdcdb9602383288cda766207fcc1b79592d
    Compiled by jenkins on 2021-10-17T00:31Z
    Compiled with protoc 2.5.0
    From source with checksum 18f47a89fe64c8a1f21a11eccdf53679
    This command was run using /usr/lib/hadoop/hadoop-common-3.2.2.jar
  
    $ hdfs dfs -ls /
    Found 7 items
    drwxr-xr-x   - hdfs  hadoop          0 2021-10-25 14:51 /apps
    drwxrwxrwx   - hdfs  hadoop          0 2021-10-25 14:51 /benchmarks
    drwxr-xr-x   - hbase hbase           0 2021-10-25 15:24 /hbase
    drwxr-xr-x   - solr  solr            0 2021-10-25 14:51 /solr
    drwxrwxrwt   - hdfs  hadoop          0 2021-10-25 14:52 /tmp
    drwxr-xr-x   - hdfs  hadoop          0 2021-10-25 14:51 /user
    drwxr-xr-x   - hdfs  hadoop          0 2021-10-25 14:51 /var

#### 4.3 Hive
    SLF4J: Class path contains multiple SLF4J bindings.
    SLF4J: Found binding in [jar:file:/usr/lib/hive/lib/log4j-slf4j-impl-2.10.0.jar!/org/slf4j/impl/StaticLoggerBinder.class]
    SLF4J: Found binding in [jar:file:/usr/lib/hadoop/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
    SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
    SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]
    Hive Session ID = 4b88b168-4d2b-4dd7-b447-7f7a3e2af5d3

    Logging initialized using configuration in jar:file:/usr/lib/hive/lib/hive-common-3.1.2.jar!/hive-log4j2.properties Async: true
    Hive Session ID = 400419ee-492e-40b1-8825-8af1af4352e1
    Hive-on-MR is deprecated in Hive 2 and may not be available in the future versions. Consider using a different execution engine (i.e. spark, tez) or using Hive 1.X releases.
    hive>
#### 4.4 Spark
    $ pyspark --master yarn
    Python 2.7.18 (default, Mar  8 2021, 13:02:45) 
    [GCC 9.3.0] on linux2
    Type "help", "copyright", "credits" or "license" for more information.
    SLF4J: Class path contains multiple SLF4J bindings.
    SLF4J: Found binding in [jar:file:/usr/lib/spark/jars/slf4j-log4j12-1.7.30.jar!/org/slf4j/impl/StaticLoggerBinder.class]
    SLF4J: Found binding in [jar:file:/usr/lib/hadoop/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
    SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
    SLF4J: Actual binding is of type [org.slf4j.impl.Log4jLoggerFactory]
    Setting default log level to "WARN".
    To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).
    21/10/26 13:13:32 WARN Client: Neither spark.yarn.jars nor spark.yarn.archive is set, falling back to uploading libraries under SPARK_HOME.
    /usr/lib/spark/python/pyspark/context.py:225: DeprecationWarning: Support for Python 2 and Python 3 prior to version 3.6 is deprecated as of Spark 3.0. See also the plan for dropping Python 2 support at https://spark.apache.org/news/plan-for-dropping-python-2-support.html.
      DeprecationWarning)
    Welcome to
          ____              __
         / __/__  ___ _____/ /__
        _\ \/ _ \/ _ `/ __/  '_/
       /__ / .__/\_,_/_/ /_/\_\   version 3.0.1
          /_/

    Using Python version 2.7.18 (default, Mar  8 2021 13:02:45)
    SparkSession available as 'spark'.
    >>>
#### 4.5 Flink
    $ flink --version
    Version: 1.11.3, Commit ID: 09d20bd
#### 4.6 Kafka
    $ kafka-topics.sh --version
    2.4.1 (Commit:unknown)
