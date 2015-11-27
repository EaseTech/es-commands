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
http://localhost:9200/_cat/nodes?v

List all Indeces in our cluster
====================
http://localhost:9200/_cat/indices?v

An index is like a ‘database’ in a relational database. It has a mapping which defines multiple types.
An index is a logical namespace which maps to one or more primary shards and can have zero or more replica shards.
MySQL => Databases => Tables => Columns/Rows
Elasticsearch => Indices => Types => Documents with Properties
An Elasticsearch cluster can contain multiple Indices (databases), which in turn contain multiple Types (tables). These types hold multiple Documents (rows), and each document has Properties(columns).

Create an Index
===========
curl -XPUT http://localhost:9200/customer?pretty - for pretty printing

Put document under Index
=================
curl -XPUT 'localhost:9200/customer/external/1?pretty' -d '
{
  "name": "John Doe"
}'
The above command creates a type(aka table) with the name external and assigns the id to value 1.

Retrieve the Document
===============
curl -XGET 'localhost:9200/customer/external/1?pretty'

Delete the Index
================
curl -XDELETE 'localhost:9200/customer?pretty'

Generic Pattern to access data in ES
==============
curl -X<REST Verb> <Node>:<Port>/<Index>/<Type>/<ID>


