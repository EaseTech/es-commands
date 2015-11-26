# es-commands
Once you have your cluster up and running, use the following commands for exploring the cluster

Health Commands
==========
http://localhost:9200/_cat/health?v -> The overall health of the cluster.
Status Options
* GREEN - Cluster is fully functional
* YELLOW - All data is available but some replicas are not yet allocated
* RED - Part of your data is not available (probably nodes for a given shard are down)

List of Nodes in our cluster
=====================
http://localhost:9200/_cat/nodes?v -> List of Nodes in our cluster

List all Indeces in our cluster
====================
http://localhost:9200/_cat/indices?v -> List all Indeces in our cluster
