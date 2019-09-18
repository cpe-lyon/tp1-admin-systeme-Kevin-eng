# Exercice 1. Variables d’environnement

## **1. Dans quels dossiers bash trouve-t-il les commandes tapées par l’utilisateur?**
*Les commandes tapées par l'utilisateur se trouvent à l'aide de "echo $PATH" :
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin**

## **2.Quelle variable d’environnement permet à la commande cd tapée sans argument de vous ramener dans votre répertoire personnel?**

*La variable d'environnement est HOME, on peut l'observer en tappant : "env".*

## **3. Explicitez le rôle des variables LANG, PWD, OLDPWD, SHELL et _.**
*La variable LANG permet de changer la langue ainsi que les caractères de l'écriture*

*La variable PWD permet de spécifier le chemin courant*

*La variable $OLDPWD contient le chemin absolu vers le répertoire courant précédent (permet de savoir d'où on vient).*

*$SHELL indique l'interpréteur shell utilisé par défaut. La valeur habituelle sous linux est /bin/bash (plus rarement /bin/sh).*

*La variable _\* indique /bin/bashbug.*

## **4.Créez une variable locale MY_VAR (le contenu n’a pas d’importance). Vérifiez que la variable existe.**

*kz@serveur:~$ MY_VAR="test" // Création de la variable local*

*kz@serveur:~$ echo $MY_VAR  
test // Test d'affichage*

## **5. Tapez ensuite la commande bash. Que fait-elle? La variable MY_VAR existe-t-elle? Expliquez. A la fin de cette question, tapez la commande exit pour revenir dans votre session initiale.**

*La commande bash permet de créer un autre shell. La variable MY_VAR n'existe plus car c'est une variable locale donc présente que sur le shell principal*

## **6. Transformez MY_VAR en une variable d’environnement et recommencez la question précédente. Expliquez.**

*On va créer la variable environnemment :*

*"kz@serveur:~$ export MY_VAR="Test""*

*En recommancant la question précèdente, on observe que cette fois-ci, la variable MY_VAR existe dans l'autre shell*

*kz@serveur:~$ bash
kz@serveur:~$ echo $MY_VAR
Test
kz@serveur:~$*

## **7. Créer la variable d’environnement NOMS ayant pour contenu vos noms de binômes séparés par un espace. Afficher la valeur de NOMS pour vérifier que l’affectation est correcte.**

*kz@serveur:~$ export NOMS="Issam Zhou"*

*kz@serveur:~$ echo $NOMS
Issam Zhou*

*L'affectation est correcte.*

## **8. Ecrivez une commande qui affiche ”Bonjour à vous deux, binôme1 binôme2!” (où binôme1 et binôme2 sont vos deux noms) en utilisant la variable NOMS.**

*kz@serveur:~$ echo Bonjour à vous deux: $NOMS*

*Bonjour à vous deux: Issam Zhou*

## **9. Quelle différence y a-t-il entre donner une valeur vide à une variable et l’utilisation de la commande unset?**

*La commande unset permet de supprimer la variable donc elle ne prends plus de mémoire tandis que mettre une variable vide prend de la mémoire et est toujours disponible dans "env"*

## **10. Utilisez la commande echo pour écrire exactement la phrase : $HOME = chemin (où chemin est votre dossier personnel d’après bash)**

*kz@serveur:~$ echo '$HOME' = $HOME
$HOME = /home/kz*

# Programmation Bash
# Vous enregistrerez vos scripts dans un dossier script que # vous créerez dans votre répertoire personnel. Tous les # scripts sont bien entendu à tester. Ajoutez le chemin vers # script à votre PATH de manière permanente.


*kz@serveur:~/script$ export PATH=$PATH:/home/kz/script*

*kz@serveur:~/script$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/kz/script*

# Exercice 2. Contrôle de mot de passe

**Écrivez un script testpwd.sh qui demande de saisir un mot de passe et vérifie s’il correspond ou non au contenu d’une variable PASSWORD dont le contenu est codé en dur dans le script. Le mot de passe saisi par l’utilisateur ne doit pas s’afficher.**

#!/bin/bash

PASSWORD=123 // *Variable qui contient le bon mot de passe*

read -p  "Saisissez le mdp :" -s a // *Permet d'afficher le texte et inserer ce qu'ecrit l'utilisateur dans la variable* 

if [ $a = $PASSWORD ] // *Condition if =*

then

        echo "Le mot de passe est bon" 

else

        echo "Le mot de passe est mauvais"

fi


# Exercice 3. Expressions rationnelles 
# Ecrivez un script qui prend un paramètre et utilise la fonction suivante pour vérifier que ce paramètre est un nombre réel :

function is_number()

{

    re='^[+-]?[0-9]+([.][0-9]+)?$'

    if ! [[ $1 =~ $re ]] ; then

        return 1

    else

        return 0

    fi

}

*On va tout d'abord créer le fichier à l'aide de :*

*"touch exercice3.sh"*

*Ensuite on va écrire le script :*


#!/bin/bash

function is_number()

{
        
        re='^[+-]?[0-9]+([.][0-9]+)?$'  // Initialisation de la variable regex qui definit les normes d'un nombre réel

        if ! [[ $1 =~ $re ]]; then  // Comparaison du nombre rentrer avec la variable re

                return 1

        else

                return 0

        fi
}

is_number $1

if [ $? = 0 ];  then

        echo " Le nombre est un réel "

else

        echo " Le nombre n'est pas un réel "

fi



# Exercice 4. Contrôle d’utilisateur Écrivez un script qui vérifie l’existence d’un utilisateur dont le nom est donné en paramètre du script.Si le script est appelé sans nom d’utilisateur,il affiche le message:”Utilisation:nom_du_scriptnom_utilisateur”, où nom_du_script est le nom de votre script récupéré automatiquement (si vous changez le nom de votre script, le message doit changer automatiquement)


#!/bin/bash

nb_user=$(cat /etc/passwd | wc -l)

for i in $(seq 1 $nb_user)

do
    	user=$(cat /etc/passwd | cut -d : -f1 | sort | head -n $i | tail -n 1)

    	if ! [ $1 ]

    	then

            	echo "Utilisation : $0 nom_utilisateur"

            	exit

    	else

            	if [ "$1" = "$user" ]

            	then

                    	echo "L'utilisateur $user existe"

                    	exit

            	fi

    	fi

done

echo "L'utilisateur $1 n'existe pas"

exit

# Exercice 5. Factorielle Écrivez un programme qui calcule la factorielle d’un entier naturel passé en paramètre (on supposera que l’utilisateur saisit toujours un entier naturel).

#!/bin/bash

read -p  "Saisissez un nombre entier :"  ent

f=1

for i in $(seq 1 $ent)

do

        f=$(($f*$i))

done

echo " La factorielle de $ent est :"$f

# Exercice 6. Le juste prix Écrivez un script qui génère un nombre aléatoire entre 1 et 1000 et demande à l’utilisateur de le deviner. Le programme écrira ”C’est plus!”, ”C’est moins!” ou ”Gagné!” selon les cas (vous utiliserez $RANDOM).

#!/bin/bash

echelle=1000

nombre=$RANDOM

let "nombre %= $echelle"

echo "Saisir un nombre (entre 1 et 1000): "

read nb

while [ $nb -ne $nombre ]

do

        if [ $nb -lt $nombre ] ; then

                echo "c'est plus + !"

        elif [ $nb -gt $nombre ] ; then

                echo "c'est moins - !"

        fi

        echo -e "\nSaisir un nombre :"

        read new
        
        nb=$new

done

if [ $nb -eq $nombre ] ; then

        echo "BRAVO vous avez trouvé le juste prix ! --> $nombre <--"

fi


# Exercice 7. Statistiques 

1. Écrivez un script qui prend en paramètres trois entiers (entre -100 et +100) et affiche le min, le max et la moyenne. Vous pouvez réutiliser la fonction de l’exercice 3 pour vous assurer que les paramètres sont bien des entiers.

 2. Généralisez le programme à un nombre quelconque de paramètres (pensez à SHIFT) 
 
 3. Modifiez votre programme pour que les notes ne soient plus données en paramètres, mais saisies et stockées au fur et à mesure dans un tableau.

