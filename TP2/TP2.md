
# UNIX

## TP n°2: Secure Shell : SSH

### 1.1 Connection ssh root (reprise fin tp-01)

Pour ce connecter en ssh, lancer la VM avec la commande ``` Vbox LicencePro2023 ```  
Maintenant que la VM fonctionne, on se connecte ``` ssh root@10.20.0.30 ```  

 <!-- récuperer le screen de man sshd_config  -->

### 1.2 Authentification par clef / Génération de clefs

Pour créer le couple de clef d'authentifiaction privé/publique ``` ssh-keygen ```  

<!-- Récuperer les screen et compléter l'explication -->

### 1.3 Authentification par clef / Connexion serveur

### 1.4 Authentification par clef : depuis la machine hôte

Pour pouvoir se connecter en utilisant la clef : ``` ssh -i (fichier clef) root@10.20.0.30 ```  

### 1.5 Sécurisez 


