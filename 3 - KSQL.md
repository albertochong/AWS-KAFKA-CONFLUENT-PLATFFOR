
# Working with KSQL basics

## Reference KSQL commands 
### https://docs.confluent.io/current/ksql/docs/developer-guide/index.html 
### https://docs.confluent.io/current/ksql/docs/tutorials/examples.html#ksql-examples

## Run in Terminal

* Check if ksql is runnig
```bash
 ps -aux | grep ksql
```

* STart ksql
```bash
 ksql
```

* Some ksql commands
```bash
1 - list topics;   ------------------------------ list all topics
    show topics;
    
2 - print 'topic_name'; -------------------------- print only all newest messages
    print 'topic_name' from beginning; ----------- print all messages
    print 'topic_name' from beginning limit n; --- print top n messages
    
3 - list properties;------------------------------ list configuration properties

4 - list functions;------------------------------- list all UDF UDAF functions
```

* Streams
```bash
0 - SET 'auto.offset.reset'= 'earliest';  ---------- to see all streams.If we close prompt,next time we should typping again

1 - Create streams from topic sintax: VALUE_FORMAT OPTIONS(DELIMITED;JSON)
    CREATE STREAM users_streams(user VARCHAR, email VARCHAR, phone VARCHAR) WITH (KAFKA_TOPIC='TpTeste', VALUE_FORMAT='DELIMITED');
   
2 - list streams;
    show streams;

3 - Query:
    select * from users_streams emit changes limit n
    
4 - Drop streams sintax:
    drop stream if exixts users_streams delete topic_name;

5 - describe stream_name; --------------- info about datatypes

6 - DESCRIBE EXTENDED stream_name;------ describe stream in detail

```

* Connectors
```bash
0 - show connetors; ---------- list all sourdcs and sink connectors

1 - DESCRIBE CONNECTOR conn1; ------------ describe connectors

2 - DROP CONNECTOR connector_name -------- drop connector

```

* Tables
```bash
0 - show Tables; ---------- list all tables

1 - DESCRIBE Table tbl; ------------ describe tables

2 - DROP TABLE tbl_name -------- drop table

```

* Logs
```bash
confluent local log ksql-server  -f   -------- check  last lines
```


![alt text](https://achong.blob.core.windows.net/gitimages/streams.PNG) 

