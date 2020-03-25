
# Working with KSQL basics

## Reference KSQL commands 
###  

## Run in Terminal

* STart ksql
```bash
 ksql
```

* Some ksql commands
```bash
1 - list topics;   ------------------------------ list all topics
2 - print 'topic_name'; -------------------------- print only all newest messages
    print 'topic_name' from beginning; ----------- print all messages
    print 'topic_name' from beginning limit n; --- print top n messages
```

* Streams
```bash
![alt text](https://achong.blob.core.windows.net/gitimages/streams.PNG) 
```


```bash
0 - SET 'auto.offset.reset'= 'earliest'  ---------- to see all streams.If we close prompt,next time we should typping again

1 - Create streams sintax:
    create streams users_streams(user VARCHAR, email VARCHAR, phone VARCHAR) WITH (KAFKA_TOPIC='TpTeste', VALUE_FORMAT='DELIMITED');

2 - list streams;

3 - Query:
    select * from users_streams limit n
```
