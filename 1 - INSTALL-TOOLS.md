# Installing Tools 
### Tools
* wget
* nano
* java
 
## Run in terminal

* Install wget
```bash
sudo yum install rsync wget net-tools
```

* Install nano
```bash
sudo yum install nano
```
    
## Install Java Virtual machine.Kafka needs jdk to work 
### Run in terminal

* Check if java is installed
```bash 
java -version 
or
sudo yum list java*
``` 

* Remove all openjdk packages
```bash 
sudo yum remove java*
``` 

* (Download Java) under home/user directory
```bash 
wget -c --content-disposition "https://javadl.oracle.com/webapps/download/AutoDL?BundleId=239835_230deb18db3e4014bb8e3e8324f81b43"
```

* Unpack 
```bash 
sudo tar xzf java_package_name
```

*  Move folder jdk1.8.0_221 to opt/jdk
```bash 
sudo mv jdk1.8.0_221/ /opt/jdk
```


*  Edit .bashrc Under home/user directory to create envirnoment variable for java and add
```bash 
nano .bashrc
  export JAVA_HOME=/opt/jdk
  export JRE_HOME=/opt/jdk/jre
  export PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
```

* Reactive and update and read news environment variable
```bash 
source .bashrc
```

* To confirm java installation
```bash 
java -version 
```    
