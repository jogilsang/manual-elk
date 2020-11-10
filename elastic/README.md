


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

-Xms256m
-Xmx256m

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
curl -XGET localhost:9200
{
  "name" : "ip-172-31-12-141",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "Gp161qVeSKuFVA1sa1w2ZA",
  "version" : {
    "number" : "7.9.3",
    "build_flavor" : "default",
    "build_type" : "deb",
    "build_hash" : "c4138e51121ef06a6404866cddc601906fe5c868",
    "build_date" : "2020-10-16T10:36:16.141335Z",
    "build_snapshot" : false,
    "lucene_version" : "8.6.2",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
}

***
journalctl -xe
```
