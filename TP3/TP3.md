
# UNIX

## TP n°3: Shell bash

### Paramètre

Script :  
![Script analyse.sh](./asset/Paramètre/analyse_sh.png)  
Résultat :  
![Résultat analyse.sh](./asset/Paramètre/Résultats.png)  


### Vérification du nombre de paramètres

Script (je l'avais mal nommé "contact.sh" au lieu de "concat.sh") :  
![Script concat.sh](./asset/verife%20nb%20para/nano_contact.png)  
Résultat :  
![Résultat concat.sh](./asset/verife%20nb%20para/resultat.png)  


### Argument type et droits

Script :  
![Script test-fichier.sh](./asset/arg%20type%20et%20droits/debut_nano.png)  
§[Script Suite](./asset/arg%20type%20et%20droits/nano.png)  
Résultat :  
![Résultat test-fichier.sh](./asset/arg%20type%20et%20droits/resultat.png)  


### Afficher le contenu d’un répertoire

Script :  
![Script listedir.sh](./asset/contenu%20rep/nano.png)  
Résultat :  
![Résultat listedir.sh](./asset/contenu%20rep/resultat.png)  


*A partir de l'exercie suivant le tp à été réalisé sur mon pc perso. J'utilise Ubuntu.*  


### Lister les utilisateurs  

``` bash
#!/bin/bash
for user in $(cat /etc/passwd); 
do echo $user; 
done 
```   
Ce script affiche le fichier passwd ligne par ligne, or on veut afficher que le login des utilisateurs qui ont un UID supérieur à  100.  
On va donc utiliser cut pour avoir uniquement les clonnes qui nous intérressent.  
Script :  
![Script avec cut](./asset/Lister%20utilisateurs/nano.png)  
Résultat :  
![Résultat avec cut](./asset/Lister%20utilisateurs/resultat.png)  
Script avec awk :  
![Script avec awk](./asset/Lister%20utilisateurs/nanoAWK.png)  
Résultat avec awk:  
![Résultat avec awk](./asset/Lister%20utilisateurs/resultatAWK.png)  


###  Mon utilisateur existe t’il  

Script :  
![Script utiexiste.sh](./asset/utilisateur%20existe/nano.png)  
![Script suite utiexiste.sh](./asset/utilisateur%20existe/nano_fin.png)  
Résultat :  
![Resultat utiexiste.sh](./asset/utilisateur%20existe/resultat.png)  ''


### Creation utilisateur  

Script :  
![Script creauti.sh](./asset/creation%20utilisateur/nano_debut.png)  
![Script suite creauti.sh](./asset/creation%20utilisateur/nano_fin_corr.png)  
Résultat :  
![Resultat creauti.sh](./asset/creation%20utilisateur/resultat.png)  
![Resultat suite creauti.sh](./asset/creation%20utilisateur/resultat2.png)  


###  Lecture au clavier

1. Essayer les commandes suivantes :  
``` bash
echo -n "Entrer votre nom: "
read nom
echo "Votre nom est $nom"
```  
![Résultat du test](./asset/lecture%20clavier/resultat_essaie_commandes.png)  
2. Teste file et more :  
![Testes](./asset/lecture%20clavier/file_more.png)  
- **Comment quitter more ?** Pour quitter more, on appuie sur "q".  
- **Comment avancer d’une ligne ?** Pour avancer d'une ligne, on appuie sur la touche "entrer" ou sur la flèche vers le bas.  
- **Comment avancer d’une page ?** Pour avancer d'une page, on appuie sur la touche "espace".  
- **Comment remonter d’une page ?** Pour remonter d'une page, on appuie sur la touche "b".  
- **Comment chercher une chaîne de caractères ? Passer à l’occurence suivante ?** Pour rechercher une chaîne de caractères, on appuie sur "/". Cela permet de saisir la chaîne que l'on souhaite rechercher, puis on appuie sur "Entrée". Pour passer à l'occurrence suivante, on appuie sur "n".  
3. Script :  
![Script clavier.sh](./asset/lecture%20clavier/script.png)  
Résultat :  
![Resultat clavier.sh](./asset/lecture%20clavier/resultat_finale.png)  


### Appréciation

Script :  
![Script appreciation.sh](./asset/appreciation/script.png)  
Résultat :  
![Resultat appreciation.sh](./asset/appreciation/resultat.png)  
