


### install
```
sudo add-apt-repository -y ppa:webupd8team/java
sudo apt-get update
sudo apt-get -y install oracle-java8-installer
java -version

wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.9.3-amd64.deb
sudo dpkg -i elasticsearch-7.9.3-amd64.deb
install : cd /usr/share/elasticsearch/
config : cd /etc/elasticsearch
init script : cd /etc/init.d/elasticsearch
sudo systemctl enable elasticsearch.service
```

### start
```
sudo service elasticsearch start
sudo service elasticsearch stop
```

