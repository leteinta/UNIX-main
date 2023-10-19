
# UNIX

## TP n°2: Secure Shell : SSH

### 1 Secure Shell : SSH

#### 1.1 Connection ssh root (reprise fin tp-01)

Pour ce connecter en ssh, lancer la VM avec la commande ``` Vbox LicencePro2023 ```  
Pour modifier sshd_config  
![nano sshd_config](./asset/nano_sshd_config)  
La configuration nécessaire pour permettre les connexions root distante avec mot de passe : trouver la ligne "#PermitRootLogin prohibit-password" et rajouter une ligne en dessous avec "PermitRootLogin yes".  
![man sshd_config](./asset/man_sshd_config.png)  
Il existe plusieurs options concernant le PermitRootLogin :  
- yes, premet la connexion à root par mot de passe.
- prohibit-password (c'est l'option par défaut), l'authentification par mot de passe est désactivée pour root.
- forced-commands-only, connexion possible par clé publique uniquement si spécifiée. Toutes les autres méthodes d'authentification sont désactivées pour root.
- no, root n'est pas autorisé à se connecter.  
Relancer ssh ``` systemctl restart ssh ```  
Maintenant que la VM fonctionne, on se connecte ``` ssh root@10.20.0.30 ```  


#### 1.2 Authentification par clef / Génération de clefs et 1.3 Authentification par clef / Connexion serveur

Pour créer le couple de clef d'authentifiaction privé/publique ``` ssh-keygen ```  
![Génération de clé publique/privé](./asset/generation_clé.png)  

Copie de la clé publique sur le serveur.  
![Envoyer la clé sur le serveur](./asset/copie_cle.png)  

Restriction du fichier authorized-keys, droit de lecture, écriture et execution pour le propriétaire seulement.  
![Droit Lecture/Ecriture/Execution](./asset/droit_ecriture_lecture_execution.png)  


#### 1.4 Authentification par clef : depuis la machine hôte

Pour pouvoir se connecter en utilisant la clef : ``` ssh -i id_rsa root@10.20.0.30 ```  
![Connexion avec clé ssh](./asset/connexion_ssh_cle.png)  


#### 1.5 Sécurisez 

On rechange le fichier sshd_config afin d'enlever la possibilité de se connecter avec le mot de passe root et on grade uniquement la connexion par clé.  
On retourne donc dans le fichier avec nano et on supprime la ligne rajouté dans le 1.1, on revient donc au fichier initiale.  
![Modification sshd_config](./asset/sshd-config_rechange.png)  
On relance ssh ``` systemctl restart ssh ```  

Les attaques dites « bruteforce SSH » sont des tentatives de connexions SSH effectuant une succession d'essais pour découvrir un couple utilisateur/mot de passe valide afin de prendre le contrôle de la machine. Il s'agit d'une attaque très répandue et toute machine exposée sur Internet se verra attaquer plusieurs fois par jour.

Quelques solutions : 
| Solutions | Avantages | nconvénients |
| :----------------------------- | :----------------------------- |:----------------------------- |
| N'autoriser que l'authentification par clé ssh. | Aucune connexion avec mot de passe root n'est demander, il faut avoir la clé. | Ne protège pas complètement le service. Certains robots peu intelligents continueront de tenter un très grand nombre de connexions, ce qui peut induire certains effets indésirables, comme une forte charge du service et le remplissage des journaux. |
| Limiter le nombre de tentative de connexion par IP. | Permet d'empêcher le robot de faire plus de x tentative par IP. | Le robot peut changer d'IP et continuer. De plus si un utilisateur se trompe de mot de passe x fois, il peux être bloqué. |
| Faire une liste blanche. | Permet d’autoriser uniquement certains IPs à se connecter. (Si l’ip du pirate n’est pas présent dans la liste la connexion lui sera refusé) | Notifier toutes les ip autorisé, ce qui peut être embêtant si notre utilisateur autorisé change de réseau constamment. |  


### 2 Processus

#### 2.1 Etude des processus UNIX

1.  
![Commande : ps aux](./asset/ps%20aux.png)  
Time : Temps total d'utilisation du processeur accumulé pour un processus particulier.  
![Commande : top](./asset/2-top%20cpu.png)  
![Commande premier processus: ps aux --sort=pid](./asset/premier%20processus.png)  
![Commande heure de démarage](./asset/heure_demarage.png)  
![Commande heure de démarage 2](./asset/heure%20demarge%202.png)  
Il y a eu approximativement 700 processus depuis le démarage ``` ps -ef ```  

2. 
![Commande PPID](./asset/ps_ppid.png)  
Le processus  avec le ppid est le 703 donc pour voir l'ancêtre :  
![Commande ps -edf | grep 703](./asset/ps%20edf%20grep.png)  

3. 
![Commande nécessaire pour installer pstree](./asset/apt%20search%20pstree.png)  
Renvoie qu'il faut installer psmisc.  
![Commande installer psmisc](./asset/apt%20install.png)  
``` pstree ```  

4. 

