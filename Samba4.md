### 0. Pourrais tu me faire un guide d'installation de Samba4 ? [SIte](https://host974.com/gpt3/)


#### 1. Vérifiez que votre système est à jour en exécutant la commande suivante :
```
sudo apt-get update && sudo apt-get upgrade
```

<br />

#### 2. Installez les paquets nécessaires pour Samba4 en exécutant la commande suivante :
```
sudo apt-get install samba krb5-user krb5-config winbind libpam-winbind libnss-winbind libpam-krb5 libpam-ccreds libpam-modules
```

<br />

#### 3. Créez un utilisateur pour Samba4 en exécutant la commande suivante :
```
sudo adduser --system --no-create-home --disabled-login --disabled-password --group samba
```

<br />


#### 4. Téléchargez la dernière version de Samba4 à partir du site officiel de Samba :
```
wget https://download.samba.org/pub/samba/stable/samba-4.14.6.tar.gz
```

<br />

#### 5. Extrayez le fichier téléchargé en exécutant la commande suivante :
```
tar -xvzf samba-4.14.6.tar.gz
```

#### 6. Accédez au répertoire extrait en exécutant la commande suivante :
```
cd samba-4.14.6
```

#### 7. Configurez Samba4 en exécutant la commande suivante :
```
./configure --enable-debug --enable-selftest
```

<br />


#### 8. Compilez Samba4 en exécutant la commande suivante :
```
make
```

<br />


#### 9. Installez Samba4 en exécutant la commande suivante :
```
sudo make install
```

<br />


#### 10. Configurez Samba4 en éditant le fichier de configuration smb.conf :
```
sudo nano /usr/local/samba/etc/smb.conf
```

<br />


#### 11. Ajoutez les paramètres de configuration nécessaires pour votre environnement Samba4.

<br />

#### 12. Démarrez le service Samba4 en exécutant la commande suivante :
```
sudo systemctl start samba
```

<br />


#### 13. Vérifiez que le service Samba4 est en cours d'exécution en exécutant la commande suivante :
```
sudo systemctl status samba
```

<br />


#### 14. Configurez Samba4 pour qu'il démarre automatiquement au démarrage du système en exécutant la commande suivante :
```
sudo systemctl enable samba
```

Et voilà, vous avez installé et configuré Samba4 sur votre système Linux ! Vous pouvez maintenant commencer à utiliser Samba4 pour partager des fichiers et des imprimantes avec d'autres ordinateurs sur 
votre réseau.
