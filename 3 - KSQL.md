
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
```

* Streams
```bash
0 - SET 'auto.offset.reset'= 'earliest';  ---------- to see all streams.If we close prompt,next time we should typping again

1 - Create streams from topic sintax: VALUE_FORMAT OPTIONS(DELIMITED;JSON)
    CREATE STREAM users_streams(user VARCHAR, email VARCHAR, phone VARCHAR) WITH (KAFKA_TOPIC='TpTeste', VALUE_FORMAT='DELIMITED');
   
2 - list streams;
    show streams;

3 - Query:
    select * from users_streams limit n
    
4 - Drop streams sintax:
    drop streams if exixts users_streams delete topic;

5 - describe stream_name; --------------- info about datatypes

```


![alt text](https://achong.blob.core.windows.net/gitimages/streams.PNG) 

