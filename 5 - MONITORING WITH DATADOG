# Monitoring Confluent Platform with Datadog
Datadog has had an Apache Kafka® integration for monitoring self-managed broker installations (and associated Apache ZooKeeper™ deployments) with their Datadog Agent for several years. The Confluent Platform integration adds several new capabilities:

Monitoring for Kafka Connect, ksqlDB, Confluent Schema Registry, and Confluent REST Proxy
Monitoring for Java-based Kafka clients
Default Confluent Platform dashboard with the most critical metrics

### Run in terminal 

* Download YUM packages for the Datadog Agent 
```bash
DD_AGENT_MAJOR_VERSION=7 DD_API_KEY=2baf15719c4e20c4903477d8da0002e7 bash -c "$(curl -L https://raw.githubusercontent.com/DataDog/datadog-agent/master/cmd/agent/install_script.sh)"
```

* Start Agent
```bash
sudo systemctl start datadog-agent
```


* Checking some properties go to
```bash
cd /etc/datadog-agent/datadog.yaml
cd /etc/datadog-agent/conf.d/ metrics.yaml
```
