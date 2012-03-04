Hadoop Plugin for ElasticSearch
==================================

The Hadoop plugin allows to use Hadoop as a shared gateway for ElasticSearch.

In order to install the plugin, simply run: `bin/plugin -install elasticsearch/elasticsearch-hadoop/1.2.0`.

    -----------------------------------------------------------------
    | Hadoop Plugin    | ElasticSearch    | Embedded Hadoop Version |
    -----------------------------------------------------------------
    | master           | 0.19 -> master   | 0.20.204.0              |
    -----------------------------------------------------------------
    | 1.2.0            | 0.19 -> master   | 0.20.204.0              |
    -----------------------------------------------------------------
    | 1.1.0            | 0.19 -> master   | 0.20.204.0              |
    -----------------------------------------------------------------
    | 1.0.0            | 0.18             | 0.20.204.0              |
    -----------------------------------------------------------------

The hadoop plugin contains embedded version of hadoop jar files to communicate with hadoop. It can be replaced with the actual version of haddop one is using.

Hadoop Gateway
--------------

The hadoop (HDFS) based gateway stores the cluster meta and indices data in hadoop. Here is an example config to enable it:

    gateway:
        type: hdfs
        hdfs:
            uri: hdfs://myhost:8022

The hadoop gateway requires two simple settings. The `gateway.hdfs.uri` controls the URI to connect to the hadoop cluster, for example: `hdfs://myhost:8022`. The `gateway.hdfs.path` controls the path under which the gateway will store the data. The `gateway.hdfs.concurrent_streams` allow to throttle the number of streams (per node) opened against the shared gateway performing the snapshot operation. It defaults to `5`.
