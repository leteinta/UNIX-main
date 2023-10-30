
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
![Script avec cut](./asset/Lister%20utilisateurs/nanoAWK.png)  
Résultat avec awk:  
![Résultat avec cut](./asset/Lister%20utilisateurs/resultatAWK.png)  