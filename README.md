# ADTool1
Create AD User by copy, give AD User informations, give AD computer informations.

MENU :
1 - Crée un utilisateur AD par copie (même OU et mêmes groupes)
2 - Rapport sur un utilisateur
3 - Rapport sur un PC

-----------------------------------------------------------------------
Le script utilse les modules suivants :

#import du module Active Directory
Import-module ActiveDirectory

#charge le module pour la confection de fenêtre
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

#chargement du module windows form pour l'affichage des messagebox
[System.Reflection.Assembly]::LoadWithPartialName("System.Windows.Forms")
--------------------------------------------------------------------------

Procédure pour script ADTool1.ps1 --> Procédure Script ADTool1.pdf
Il y a quelques infos également en commentaire dans le script.

Ce script a été testé de mon coté et utilisé en environnement de travail mais je sais que vous savez qu'il faut bien sur 
jeter un oeil sur le contenu de tout nouveau script et le tester sur une VM test :)

------------------------------------------------------------------------------
Script pour convertir un fichier image en fichier texte :

$FilePath = "chemin vers le fichier .jpg"
#exemple : C:\image.jpg"
$SaveTo = "C:\image.txt"
[byte[]]$Data = Get-Content $FilePath -Encoding Byte
[system.convert]::ToBase64String($Data) | Set-Content $SaveTo
------------------------------------------------------------------------------

Modifier le script pour spécifier dans quelle unité organisationnelle le nouvel utilisateur sera créé :

ligne 374 du script, ajouter la ligne suivante en adaptant l'OU désiré :
-Path "OU=Utilisateurs, OU=Dossier, DC=truc, DC=local"


