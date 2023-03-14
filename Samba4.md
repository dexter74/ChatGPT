--------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Question 0. Pourrais tu me faire un guide d'installation de Samba4 ? [SIte](https://host974.com/gpt3/)

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
### 0. Pré-requis

##### A. Sources.list
```
sed -i -e "s/^deb cdrom/#deb cdrom/g" /etc/apt/sources.list;
apt install -y sudo;
```

##### B. Python
```
apt install -y libreadline-gplv2-dev; # PROBLEM
apt install -y libncursesw5-dev
apt install -y libssl-dev
apt install -y libsqlite3-dev
apt install -y libgdbm-dev
apt install -y libc6-dev
apt install -y libbz2-dev
apt install -y libffi-dev zlib1g-dev
apt install -y tk-dev
apt install -y wget;
apt install -y build-essential;

wget https://www.python.org/ftp/python/3.9.1/Python-3.9.1.tgz; tar xzf Python-3.9.1.tgz; cd Python-3.9.1;
./configure --enable-optimizations; make -j$(nproc); make alt install;
python3.9 --version;
```
 
--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 1. Vérifiez que votre système est à jour en exécutant la commande suivante :
```
apt update;
apt upgrade -y;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 2. Installez les paquets nécessaires pour Samba4 en exécutant la commande suivante :
```
apt install -y samba;
apt install -y krb5-user;
apt install -y krb5-config;
apt install -y winbind;
apt install -y libpam-winbind;
apt install -y libnss-winbind;
apt install -y libpam-krb5;
apt install -y libpam-ccreds;
apt install -y libpam-modules;
```


<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 3. Créez un utilisateur pour Samba4 en exécutant la commande suivante :
```
/usr/sbin/adduser  --system --no-create-home --disabled-login --disabled-password --group samba;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 4. Téléchargez la dernière version de Samba4 à partir du site officiel de Samba :
```
wget https://download.samba.org/pub/samba/stable/samba-4.14.6.tar.gz;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 5. Extrayez le fichier téléchargé en exécutant la commande suivante :
```
tar -xvzf samba-4.14.6.tar.gz;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 6. Accédez au répertoire extrait en exécutant la commande suivante :
```
cd samba-4.14.6;
```

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 7. Configurez Samba4 en exécutant la commande suivante :
```
./configure --enable-debug --enable-selftest;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 8. Compilez Samba4 en exécutant la commande suivante :
```
make;
```

<br />


#### 9. Installez Samba4 en exécutant la commande suivante :
```
make install;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 10. Configurez Samba4 en éditant le fichier de configuration smb.conf :
```
nano /usr/local/samba/etc/smb.conf;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 11. Ajoutez les paramètres de configuration nécessaires pour votre environnement Samba4.

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 12. Démarrez le service Samba4 en exécutant la commande suivante :
```
systemctl start samba;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 13. Vérifiez que le service Samba4 est en cours d'exécution en exécutant la commande suivante :
```
systemctl status samba;
```

<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 14. Configurez Samba4 pour qu'il démarre automatiquement au démarrage du système en exécutant la commande suivante :
```
systemctl enable samba;
```
<br />

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 15. Résumé
```
Et voilà, vous avez installé et configuré Samba4 sur votre système Linux !
Vous pouvez maintenant commencer à utiliser Samba4 pour partager des fichiers et des imprimantes avec d'autres ordinateurs sur votre réseau.
```
