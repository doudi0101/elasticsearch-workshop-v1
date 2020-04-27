### Connexion à votre instance linux

- Vos Credentials et IP respectives vous seront envoyés sur le chat
- Installer [mobaXterm](https://download.mobatek.net/2022020030522248/MobaXterm_Portable_v20.2.zip) si vous êtes sur Windows
- Une clé SSH .pem vous sera transmise sur le chat
- si elle fournie au format .pem : 
	Convertissez-la en .ppk(voir mini [tuto](https://download.mobatek.net/2022020030522248/MobaXterm_Portable_v20.2.zip))
	
### Production Tools

- Installer les outils suivants : 
- [VS Code](https://code.visualstudio.com/download)
- [GitHub Desktop](https://help.github.com/en/desktop/getting-started-with-github-desktop/installing-github-desktop)
- [ElasticSearch - The Definitive Guide ](https://drive.google.com/open?id=1dtJhgRiVfaTrqpDqi4MA4HRK5K2iWSr6)
- L'ouvrage vous est fourni à titre de démo, merci de penser aux auteurs et de l'acheter légalement

### Installation ElasticSearch
```
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.6.2-x86_64.rpm
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.6.2-x86_64.rpm.sha512
shasum -a 512 -c elasticsearch-7.6.2-x86_64.rpm.sha512 
sudo rpm --install elasticsearch-7.6.2-x86_64.rpm
```

