# KAFKA Confluent Platform MultiBroker Installation and Configuration
Cluster with 2 brokers in same server

### Run in terminal 

* Download Confluent under home/user directory
```bash
wget packages.confluent.io/archive/5.4/confluent-5.4.1-2.12.tar.gz
```

* unpack files
```bash
tar -xvf confluent-5.4.1-2.12.tar.gz
```

* move to folder opt/
```bash
sudo mv confluent-5.4.1-2.120/ /opt 
```
![alt text](https://achong.blob.core.windows.net/gitimages/confluent_folder.PNG)


* Add confluent envirnoment variables under home/user
```bash  
nano .bash_profile
 
#CONFLUENT
export CONFLUENT_HOME=/opt/confluent-5.4.1
export PATH=$PATH:$CONFLUENT_HOME/bin
```     

* Renitialize/Activate
```bash   
source .bash_profile
``` 
 
* Create broker 1.Go to <CONFLUENT_HOME>/etc/kafka installation.
```bash   
cp  server.properties  server1.properties
``` 

* Edit Broker 0.Go to <CONFLUENT_HOME>/etc/kafka installation.
```bash   
nano server.properties
listeners=PLAINTEXT://ec2-3-17-3-207.us-east-2.compute.amazonaws.com:9092
log.dir=/tmp/kafka-logs
zookeeper.connect=localhost:2181
``` 

* Edit Broker 1.Go to <KAFKA_HOME> installation and config folder.
```bash   
nano server1.properties
broker.id=1
listeners=PLAINTEXT://ec2-3-17-3-207.us-east-2.compute.amazonaws.com:9093
log.dir=/tmp/kafka-logs1
zookeeper.connect=localhost:2181
``` 

* Install the Confluent CLI
```bash   
curl -L https://cnfl.io/cli | sh -s -- -b /$CONFLUENT_HOME/bin
``` 

* Install Confluent Hub client
```bash   
wget http://client.hub.confluent.io/confluent-hub-client-latest.tar.gz?_ga=2.258297162.1562681204.1585092022-124618927.1584719496
``` 

* unpack files
```bash
tar -xvf  confluent-hub-client-latest.tar
```

* move content of bin folder to /$CONFLUENT_HOME/bin
```bash
sudo mv confluent-hub/ /$CONFLUENT_HOME/bin
```

* Start platform
```bash
confluent local start
```
![alt text](https://achong.blob.core.windows.net/gitimages/start_confluent.PNG)

P.s:
1 - If status is like this
![alt text](https://achong.blob.core.windows.net/gitimages/connect_down.PNG)
Check this property plugin.path = ...  on /etc/kafka/connect-distributed.properties and ./etc/kafka/connect-standalone.properties
Should be plugin.path = <CONFLUENT_HOME>/share/java



* Start ksql
```bash
ksql
```
![alt text](https://achong.blob.core.windows.net/gitimages/ksql.PNG)

* Start Confluent center 
```bash
control-center-start /opt/confluent-5.4.1/etc/confluent-control-center/control-center.properties
```
![alt text]()




