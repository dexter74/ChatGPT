Bien sûr, voici un guide étape par étape pour installer Samba en tant que contrôleur de domaine sous Debian 11 :

1. Mettre à jour le système :
     ```
     sudo apt update
     sudo apt upgrade
     ```

2. Installer Samba :
     ```
     sudo apt install samba
     ```

3. Configurer le fichier smb.conf :
     ```
     sudo nano /etc/samba/smb.conf
     ```
     Ajouter les lignes suivantes à la fin du fichier :
     ```
     [global]
     workgroup = NOM_DU_DOMAINE
     netbios name = NOM_DU_SERVEUR
     server role = active directory domain controller
     dns forwarder = ADRESSE_IP_DU_SERVEUR_DNS

     [netlogon]
     path = /var/lib/samba/sysvol/NOM_DU_DOMAINE/scripts
     read only = no

     [sysvol]
     path = /var/lib/samba/sysvol
     read only = no
     ```

4. Créer un utilisateur administrateur pour le domaine :
     ```
     sudo samba-tool user add ADMINISTRATEUR_DU_DOMAINE --random-password
     ```

5. Démarrer le service Samba :
     ```
     sudo systemctl start samba-ad-dc
     ```

6. Vérifier que le service est bien démarré :
     ```
     sudo systemctl status samba-ad-dc
     ```

7. Configurer le service Samba pour qu'il démarre automatiquement au démarrage du système :
     ```
     sudo systemctl enable samba-ad-dc
     ```

8. Configurer le pare-feu pour autoriser les connexions Samba :
     ```
     sudo ufw allow Samba
     ```

Et voilà, vous avez maintenant installé Samba en tant que contrôleur de domaine sous Debian 11 ! Vous pouvez maintenant ajouter des utilisateurs et des ordinateurs au domaine en utilisant la commande samba-tool.

Posez une autre question

10386 Requêtes.
