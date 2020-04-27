### Connexion à votre instance linux

- Installer [mobaXterm](https://download.mobatek.net/2022020030522248/MobaXterm_Portable_v20.2.zip) si vous êtes sur Windows
- Vos Credentials et IP respectives vous seront envoyés sur le chat
- Une clé SSH .pem vous sera transmise sur le chat
- si elle fournie au format .pem : 
	Convertissez-la en .ppk(voir mini [tuto](https://stackoverflow.com/questions/3190667/convert-pem-to-ppk-file-format))
- username : centos
- adresse ip : votre adresse
- options de connection : clé ssh ppk
	
### Production Tools

- Installer les outils suivants : 
	- [VS Code](https://code.visualstudio.com/download)
	- [GitHub Desktop](https://help.github.com/en/desktop/getting-started-with-github-desktop/installing-github-desktop)
	- [ElasticSearch - The Definitive Guide ](https://drive.google.com/open?id=1dtJhgRiVfaTrqpDqi4MA4HRK5K2iWSr6)
- IMPORTANT : L'ouvrage vous est fourni à titre de démo, merci de penser aux auteurs et de l'acheter légalement

### Installation de Java
```
sudo yum install -y java
```

### Installation ElasticSearch
```
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.6.2-x86_64.rpm
sudo rpm -i elasticsearch-7.6.2-x86_64.rpm
```
### Démarrage Service ElasticSearch
```
sudo service elasticsearch start
```

### Installation Logstash
```
wget https://artifacts.elastic.co/downloads/logstash/logstash-7.6.2.rpm
sudo rpm -i logstash/logstash-7.6.2.rpm
```

### Installation Kibana
```
wget https://artifacts.elastic.co/downloads/kibana/kibana-7.6.2-x86_64.rpm
sudo rpm -i kibana-7.6.2-x86_64.rpm
```

#### Configuration accès distant (remplacer localhost / 127.0.0.1 par 0.0.0.0) 

- Editer le fichier de conf
```
vi /home/ec2-user/kibana-7.0.0-linux-x86_64/config/kibana.yml
``` 
```
# Kibana is served by a back end server. This setting specifies the port to use.
server.port: 5601 <<<<<< VERIFIER CA

# Specifies the address to which the Kibana server will bind. IP addresses and host names are both valid values.
# The default is 'localhost', which usually means remote machines will not be able to connect.
# To allow connections from remote users, set this parameter to a non-loopback address.
server.host: 0.0.0.0 <<<<<< CHANGER CA
```

- Sauvegarder

### Démarrage Service Kibana
```
sudo service elasticsearch kibana
```

### Vérification de votre accès Web

- http://votre.adresse.IP:5601
