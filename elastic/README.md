


### 1. java install
```
sudo add-apt-repository -y ppa:webupd8team/java
sudo apt-get update
sudo apt-get -y install oracle-java8-installer
java -version
```

### 2. elastic install
```
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.9.3-amd64.deb
sudo dpkg -i elasticsearch-7.9.3-amd64.deb

***
install : cd /usr/share/elasticsearch/
config : cd /etc/elasticsearch
init script : cd /etc/init.d/elasticsearch
```

### 3. config setting
```
sudo nano /etc/elasticsearch/elasticsearch.yml

# Set the bind address to a specific IP (IPv4 or IPv6):
#
network.host: 127.0.0.1
#
# Set a custom port for HTTP:
#
http.port: 9200

sudo vi /etc/elasticsearch/jvm.options

# Xms represents the initial size of total heap space
# Xmx represents the maximum size of total heap space

-Xms128m
-Xmx128m

***
https://stackoverflow.com/questions/58656747/elasticsearch-job-for-elasticsearch-service-failed/58656748
```

### 4. start
```
sudo systemctl enable elasticsearch.service
sudo service elasticsearch start

***
sudo service elasticsearch stop
```

### 5. detect
```
journalctl -xe
```
