# Snapshot Server Operators

This document is intended as a guide for understanding and using the Snapshot Server operators.

Introduction
------------

The Snapshot Server is the operator which houses the most recent
snapshot of tabular data. The Snapshot Server receives queries from an
embedded query operator and sends query results to a result
operator. The most recent tabular data can be sent in two forms: a
list of maps and a list of POJOs. We will now describe how to
visualize both forms of tabular data.


AppDataSnapshotServerMap
------------------------

The AppDataSnapshotServerMap operator accepts a list of maps. Each map
represents a row of a table. Each key in the map represents a column
of the table and each value represents the value of a column for a
particular row. The name, and type of each column is specified through
the snapshotSchemaJSON property. The following is an example of a
snapshotSchema:

```json
{
  "values": [
    {"name": "word", "type": "string"}, 
    {"name": "count", "type": "integer"}
  ]
}
```

Here you can see that the table has two columns word and count of
types string and integer respectively. According to this schema it is
expected that the Maps in the provided list of Maps will have values
for the keys “word” and “count”.

Now that the Snapshot server is configured we need to connect the
embedded query operator and the result operator. The code snippet
below shows how to do this:

```java
String gatewayAddress = dag.getValue(DAG.GATEWAY_CONNECT_ADDRESS);
URI uri = URI.create("ws://" + gatewayAddress + "/pubsub");

AppDataSnapshotServerMap snapshotServer = dag.addOperator("SnapshotServer", new AppDataSnapshotServerMap());
snapshotServer.setSnapshotSchemaJSON(snapshotServerJSON);

PubSubWebSocketAppDataQuery wsQuery = new PubSubWebSocketAppDataQuery();
wsQuery.setUri(uri);
wsQuery.setTopic(“query”);
snapshotServer.setEmbeddableQueryInfoProvider(wsQuery);

PubSubWebSocketAppDataResult wsResult = dag.addOperator("QueryResult", new PubSubWebSocketAppDataResult());
wsResult.setUri(uri);
wsResult.setTopic(“result”);

dag.addStream("Result", snapshotServer.queryResult, queryResultPort);
```

Note that the `dt.attr.GATEWAY_CONNECT_ADDRESS` property needs to be
specified in the dt-site.xml and must contain the gateway’s ip
address. This value will be automatically set if the application is
launched through dtGateway.

AppDataSnapshotServerPOJO
-------------------------

The AppDataSnapshotServerPOJO operator accepts a list of POJOs. Each
POJO represents a row of a table. Each field of the POJO represents
represents the value for a particular column. The
AppDataSnapshotServerPOJO is configured in the same way as the
AppDataSnapshotServerMap except that there is an addition property
that must be set. This additional property is fieldToGetter
property. The fieldToGetter property is a Map from String to
String. The key is the name of a column as defined in the SchemaJSON
string. The value is the java getter method that is required to
extract the value of that column. Let’s walk through an example of a
valid setting for fieldToGetter. If this schema is configured:

```json
{
  "values": [
    {"name": "word", "type": "string"}, 
    {"name": "count", "type": "integer"}
  ]
}
```

A valid setting for fieldToGetter would be this:

```java
fieldToGetter.put(“word”, “getWord()”);
fieldToGetter.put(“count”, “getCount()”);
```

Examples
--------

Please look at the following java code for example usages of the
operators mentioned above:

https://github.com/apache/incubator-apex-malhar/blob/master/demos/pi/src/main/java/com/datatorrent/demos/pi/ApplicationAppData.java
https://github.com/apache/incubator-apex-malhar/blob/master/demos/twitter/src/main/java/com/datatorrent/demos/twitter/TwitterTrendingHashtagsApplication.java


