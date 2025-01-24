# userAdd

#!/bin/bash

#Vérifie l'argument
if [ "$#" -eq 0 ]; then #Si l'argument est vide
    echo "Argument manquant"
    exit 1
fi
#Recherche et création de l'utilisateur
for usr_nam in "$@"; do #prend en compte plusieur arguments
    #Vérifie si l'utilisateur existe
    if id "$usr_nam" &>/dev/null; then
    echo " l'utilisateur $usr_nam existe déjà"
    #Création des utilisateurs
    else
    sudo useradd "$usr_nam"
    echo "l'utilisateur $usr_nam ajouté avec succès"
    fi
done > "$usr_nam"
