# **Exercice 2** :
# **Manuel** :

### **1. A l’aide du manuel, identifiez le rôle de la commande which.**

*Pour accéder au manuel de which :
"man which"
La commande which va permettre de localiser une commande.*

### **2. Quand on consulte cette page, comment peut-on rechercher, par exemple, le mot option ?** 

*Pour rechercher un mot, on tape le mot recherché précedé de slash :
"/option*".

### **3. Comment quitte-t-on le manuel ?**

*Pour quitter le manuel, on appuie sur la touche q*.

### **4. Chaque section du manuel a une première page, qui présente le contenu de la section. Aﬀicher la première page de la section 6; De quoi parle cette section ?**

*Chaque section a une première page qui présente le contenu de la section, pour exemple, pour afficher la première page de la section 6 :
"man 6 intro"*
Cette section parle de tout les programmes et jeux amusants qui existent sur le système.

# **Naviguation dans l'arborescence des fichiers :**
### **1. allez dans le dossier /var/log**
*Pour accéder au dossier /var/log :
"cd /var/log".*

### **2. Remontez dans le dossier parent (/var) en utilisant un chemin relatif**
*Pour remonter dans le dossier parent /var en utilisant un chemin relatif :
"cd ..".*

### **3.Retournez dans le dossier personnel**
*Pour retourner dans le dossier personnel :
"cd".*

### **4. Revenez au dossier précédent (/var)**
*Pour retourner dans le dossier précedent, on tape la commande : "cd /var/" ".*

### **5. Essayez d’accéder au dossier /root; que se passe-t-il ?**
*Il est aussi impossible d'accéder à cd /root car on n'a pas la permission.*

### **6. Essayez la commande sudo cd /root; que se passe-t-il ? Expliquez**
*La commande sudo cd /root permet de passer en mode administrateur mais il ne se passe toujours rien après avoir taper notre mot de passe.*

### **7. A partir de votre dossier personnel, créez l’arborescence suivante :**
*Pour créer un dossier personnel : "mkdir Dossier"
Ensuite on accède au dossier crée avec :
"cd Dossier"*

*Création d'une arborescence :*

*Pour la création d'une arborescence, on va utiliser la commande "mkdir" suivi du nom pour chaque dossier que on souhaite créer, si c'est un sous dossier il faudra le créer à l'intérieur d'un dossier.*

### **8. Revenez dans votre dossier personnel; A l’aide de la commande rm, essayez de supprimer Fichier1, puis Dossier1; Que se passe-t-il**
*Il est impossible de supprimer le Dossier car la touche rm permet de supprimer des fichiers.*  

### **9. Quelle commande permet de supprimer un dossier?**
*La commande rmdir permet de supprimer un dossier vide.*

### **10. que se passe-t-il quand on applique cette commande à Dossier2?**
*Il est impossible de supprimer le Dossier 2 directement avec "rm Dossier/Dossier2" car le dossier 2 contient des sous dossier.*

### **11. comment supprimer en une seule commande Dossier2 et son contenu?**
*On peut forcer la suppression avec " rm -r Dossier/Dossier2 ".*
# **Commandes Importantes :**

### **1. Quelle commande permet d’aﬀicher l’heure ? A quoi sert la commande time ?**
 *Pour afficher la date, on utilise la commande :
"date".*

 *La commande time permet de mesurer le temps d'exécution d'une commande. Elle fournit les temps réels (temps total), utilisateurs (durée nécessaire au processeur pour exécuter les ordres du programme) et systèmes (durée nécessaire au processeur pour traiter les ordres du système d'exploitation).*
### **2. Dans votre dossier personnel, tapez successivement les commandes ls puis la; que peut-on en déduire sur les fichiers commençant par un point ?**
*Les fichiers commançant par un point sont les fichiers cachés.*

### **3. Où se situe le programme ls ?**
*Le programme LS se trouve dans /usr/bin.*

### **4. Que fait la commande ll? (indice : la commande alias peut vous aider)**
*La commande ll est un alias de ls -alF.*

*C'est une combinaison de a+l+F,
Elle permet de :*

*1\ Afficher tous les fichiers des répertoires, y compris les fichiers commençant par un « . ».*

*2\ En plus du nom, afficher le type du fichier, les permissions d'accès, le nombre de liens physiques, le nom du propriétaire et du groupe, la taille en octets, et l'horodatage. 
La ligne de résumé utilise des unités de 512 octets. Les types de fichiers sont indiqués par les caractères suivants : - pour les fichiers ordinaires, d pour un répertoire (directory), b pour un fichier spécial en mode bloc, c pour un fichier spécial en mode caractère, l pour un lien symbolique, p pour une fifo (named pipe), s pour une socket.
Par défaut, l'horodatage présenté est celui de la dernière modification du fichier. Les options -c et -u réclament les autres horodatages. Pour les fichiers spéciaux, le champ de taille est généralement remplacé par les numéros majeur et mineur du périphérique.*

3\ *Ne pas trier le contenu des répertoires, l'afficher dans l'ordre où il se présente sur le disque. Active les options -a et -U et désactive -l, --color -s, et -t.*

### **5. Quelle commande permet d’aﬀicher les fichiers contenus dans le dossier /bin ?**
*Une fois dans le dossier bin, la touche "ls" va permettre d'afficher tous les fichiers contenus dans "bin".*

### **6. Que fait la commande ls ..?**
*La commande ls permet d'obtenir la liste et les caractéristiques des fichiers contenus dans un répertoire.*

### **7. Quelle commande donne le chemin complet du dossier courant ?**
*La commande pwd permet de donner le chemin complet du dossier courant*.

### **8. Que fait la commande echo 'yo' > plop exécutée 2 fois ?**
*La commande  echo 'yo' > plop exécutée 2 fois permet de créer le dossier plop et d'écrire dedans yo qu'une seule fois, pour le visualiser :
"Nano plop".*

### **9. Que fait la commande echo 'yo' >> plop exécutée 2 fois ?**
*La commande echo 'yo' >> plop exécutée 2 fois permet de créer le dossier plop et d'écrire à l'intérieur yo par rapport au nombre de fois ou on execute la commande.*

### **10. A quoi sert la commande file ? Essayez la sur des fichiers de types différents.**
*File est une commande UNIX qui permet de déterminer le type d'un fichier.*

### **11. Créez un fichier toto qui contient la chaîne Hello Toto !; créer ensuite un lien titi vers ce fichier aveclacommandeln toto titi.Modifiezàprésentlecontenudetotoetaﬀichezlecontenudetiti: qu’observe-t-on? Supprimez le fichier toto; quelle conséquence cela a-t-il sur titi ?**
*On va tout d'abord créer un fichier à l'aide de la touche :
"touch" puis on va insérer la chaine avec : echo "Hello toto" > toto.*

*Ensuite on va créer un lien titi vers ce fichier à l'aide de la commande "ln toto titi"*

*Puis on va modifier le fichier toto et on observe que suite à la modification du contenu du fichier toto, le fichier titi s'est modifié automatiquement pour avoir le meme contenu que toto*

*Maintenant, on va supprimer le fichier toto et on observe que le fichier titi est resté intacte malgré la suppresion du fichier toto.*

### **12. Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi; quelle conséquence cela a-t-il sur tutu ?**
*On va créer un lien symbolique à l'aide de la commande : 
"ln - s titi tutu".*

*Ensuite on va modifier le contenu de titi et on observe que tutu a le même contenu que titi à chaque modification de titi.*

*Maintenant si on modifie le contenu de tutu, on voit que le contenu de titi est automatiquement modifier pour être comme celle de tutu.*

*On va ensuite supprimer le fichier titi, suite à celà, le fichier tutu existe toujours mais son contenu à disparu.*

### **13. Aﬀichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran ?**
*Le raccourci clavier ctrl+s permet d'arreter le defilement et ctrl+q permet de le reprendre*

### **14. Aﬀichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20.**
*Pour affichier 5 premières lignes du fichier /var/log/syslog,on va utiliser la commande : "head -5 syslog"  
Puis pour les  15 dernières :"tail -15 syslog",
Et seulement les lignes 10 à 20:"sed -n '10,20p' syslog".*

### **15. Que fait la commande dmesg | less ?**
*La commande "dmesg | less"  est une commande sur les systèmes d'exploitations de type Unix qui affiche la mémoire tampon de message du noyau accoupler à | less qui est une commande Unix qui permet de visualiser un fichier texte page par page.*

### **16. Aﬀichez à l’écran le fichier /etc/passwd ; Que contient-il ? Quelle commande permet d’aﬀicher la page de manuel de ce fichier ?**
*Le fichier /etc/passwd contient toutes les informations relatives aux utilisateurs (login, mots de passe, ...).
Passwd permet aussi de modifier le mot de passe d'un utilisateur.
La page de manuel de ce fichier peut être afficher à l'aide de "man passwd."*

### **17. Aﬀichez seulement la première colonne triée par ordre alphabétique inverse**
*La commande "sort -k 1 -d -r passwd" va permettre de trier la premier colonne dans l'ordre inverse de l'alphabet.*

### **18. Quelle commande nous donne le nombre d’utilisateurs ?**
*La commande "w" permet de voir le nombre d'utilisateur.*

### **19. Combien de pages de manuel comportent le mot-clé conversion dans leur description ?**
*"man -k conversion" va permettre d'afficher le nombre de page contenant le mot conversion dans le résumé.
Il y en a 4.*

### **20. A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine**
*La touche " find / -name passwd " va permettre de rechercher tous les fichiers se nommant passwd présent sur la machine.*

### **21. Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier ~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null**
*La commande : "find / -name passwd > ~/list_passwd_files.txt 2>> /dev/null" va permettre que la liste des fichiers trouvés soit enregistrée dans le fichier ~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/nulli.*

### **22. Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment**
*A l'aide de la commande : "grep "ll" -r" on trouve tous les endroits ou le caractère ll apparait.
On trouve l'alias ll dans : " .bashrc:alias ll='ls -alF' ".*

### **23. Utilisez la commande locate pour trouver le fichier history.log.**
*La commande locate a permis de trouver le fichier history.log :
kz@serveur:~$ locate history.log
/var/log/apt/history.log*.

### **24. Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver.Apparaît-il?Pourquoi?**
*Création du fichier question avec la commande " touch question ", on observe que avec la commande " locate fichier " on ne trouve pas le fichier car la base de donné n'a pas été mis à jour, pour celà il faut executer la commande :
"updatedb".*
