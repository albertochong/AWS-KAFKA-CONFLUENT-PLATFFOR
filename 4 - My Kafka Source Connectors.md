![alt text](https://achong.blob.core.windows.net/gitimages/kfka_connect.jpg)


# My Kafka Source Connectors
This part is dedicated to describe my own source connectors

## Create Kafka connector source to SQL SERVER
Get data and write to topic first with bulkload and after incrememtal and update.

* Check confluent platform status
```bash
confluent local status
```
![alt text](https://achong.blob.core.windows.net/gitimages/start_confluent.PNG)

* list existing connectors
```bash
confluent local list connectors
```
![alt text](https://achong.blob.core.windows.net/certificates/list_connectors.PNG)

* Making the JDBC connector available to Kafka Connect

```bash
1 - Download mssql-jdbc-7.2.1.jre8.jar from https://docs.microsoft.com/en-us/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15

2 - Put the JDBC driver downloaded above in the same folder as the Kafka Connect JDBC plugin
    Should be <CONFLUENT_HOME>/shared/java

3 - Restart the Kafka Connect worker
```

* Go to <CONFLUENTE_HOME>/etc/kafka-connect-jdbc and create your connecto to SQL SERVER instance to get data to topic
```bash
nano source-sqlserver-dbLisbonMetropolitan.properties
```
![alt text](https://achong.blob.core.windows.net/gitimages/connector_source_sqlserevr.PNG)


* Check counting records on sql database and later check messages on kafka topic
![alt text](https://achong.blob.core.windows.net/gitimages/sql_server_buslisbon.PNG)


* Load connector
```bash
    confluent local load source-sqlserver-dbLisbonMetropolitan -- -d /opt/confluent-5.4.1/etc/kafka-connect-jdbc/source-sqlserver-dbLisbonMetropolitan.properties
```
![alt text](https://achong.blob.core.windows.net/gitimages/load_source_connectoe_sql.PNG)

* Check connector status
```bash
  confluent local status source-sqlserver-dbLisbonMetropolitan
```
![alt text](https://achong.blob.core.windows.net/gitimages/sql_server_buslisbon_status.PNG)


