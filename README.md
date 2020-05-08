# AWS-KAFKA-CONFLUENT-PLATFORM
Create Messaging environment with Kafka Confluent Paltform Multi broker on AWS machine


## Create 1 Instance (t2.Xlarge) with the options
* AMI: Amazon Red Hat Linux 8 AMI (HVM), SSD Volume Type 64 bit
* Network: vpc by default + No precense subnet + Public IP Use subnet  setting (enable)
* Storage: Root disk 40 GB + Add Volume 100GB Magnetic (delete on termination)
* Use security group created (ClsKsqlChong)
* Create or use new .pem key (copy this file in a secure place)

## Security

### Create a Security Group

* Create new security group with the name: ClsKsqlChong
```bash
Type              Protocol        Port        Source

All Traffic       All             0 - 65535   Anywhere   

SSH               TCP             22          Anywhere
```

## 1. Step: Install some tools
  * Install wget
  * Install nano
  * Install Java

## 2. Step: Kafka Confluent Installation and Configuration
  * Install and Configure Kafka Confluent Multibroker 
  
### 2.1 Step: Working with KAFKA
  *  Create,describe topic
  *  Testing producer messages to the topic
  *  Testing consumer messages from the topic
  *  Generate some data to topic
  *  List Kafka availables connectors
  
## 3. KSQL
  * Create streams, table
 
## 4. My Kafka Source Connectors
  * Create source connector with JDBC to SQL SERVER instance
  
## 5.Monitoring Confluent Platform with Datadog
  * Installation and Configuration
  
