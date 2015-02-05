# Introduction à Linux RAQ - Cours 02
Eric Normandeau - 2015-02-05  
(**Version NON terminée**)

# Plan de cours
1. Introduction
1. Dossiers importants
1. Commandes utiles
1. Redirection
1. Pipelines
1. Mot de la fin
1. Exercices
1. Liste de commandes importantes

# 1 - Introduction
- Continue exploration des commandes importantes
- Considérer vieille matière aquise (mais posez des questons au besoin)
- Jouer avec redirection
- Apprendre pipelines
- Début manipulation de texte

# 2 - Dossiers importants
Voici un très court résumé des dossiers système et des dossiers spéciaux que
nous avons déjà vu.


## 2.1 - Dossiers systèmes
Il est intéressant de savoir un peu ce que contiennent les dossier qui se
trouvent à la racine, mais ça n'est pas essentiel pour utiliser Linux.

- **`/`** : Racine du système
- **`/bin`** : Programmes pour les utilisateurs (*binaries*)
- **`/dev`** : Liens vers composantes physiques (*devices*)
- **`/etc`** : Fichiers de configuration Linux et logiciels
- **`/home`** : Dossiers des utilisateurs (*user home folders*)
- **`/lib`** : Libraries pour logiciels
- **`/media`** : Disques durs externes ou réseau...
- **`/mnt`** : Vieut nom pour **`/media`**
- **`/opt`** : Applications optionelles
- **`/proc`** : Information des processus et du système
- **`/root`** : Dossier de l'utilisateur **`root`** (administrateur)
- **`/run`** : Services en cours d'utilisation (eg : serveur **`ssh`**)
- **`/sbin`** : Programmes du système (*binaries*)
- **`/srv`** : Services (eg : serveur **`ssh`**)
- **`/sys`** : Fichiers utiles au système
- **`/tmp`** : Fichiers temporaires
- **`/usr`** : Programmes des utilisateurs
- **`/var`** : Fichiers divers (logs, packages, bases de données...)

## 2.2 - Dossiers spéciaux
- **`.`**
- **`..`**
- **`~`**
- **`/`**
- **`-`**

# 3 - Commandes utiles
- **`history`** : Lister les commandes utilisées
- **`man`** : Lire le manuel d'une commande
- **`top`** : Visualiser ressources et programmes
- **`echo`** : Afficher du texte à l'écran
- **`clear`** : Vider le terminal (aussi **`Ctrl-L`**)
- **`sleep`** : Attendre pour un lapse de temps (secondes, minutes...)
- **`Ctrl-C`** : Canceller une commande
- **`Ctrl-D`** : Sortir d'un programme ou arrêter le terminal

# 4 - Redirection
- **`>`**
- **`>>`**
- **`<`**
- **`2>`**
- **`2>&1`**
- **`tee`**

# 5 - Pipelines
- Use alice.txt and sequences
- Basic for now (ie: grep | wc)

# 6 - Mot de la fin
## 6.1 - Aujourd'hui
- Qu'est-ce qu'on a vu

## 6.2 - Prochain cours
- Qu'est-ce qu'on va voir

## 6.3 - Questions et suggestions
N'hésitez pas à me poser vos questions durant les cours ou par courriel. Je
vais tenter d'y répondre durant les cours. Je vais aussi prendre vos
suggestions en note pour tenter d'améliorer le cours.

# 7 - Exercices
- ...


\newpage


# 8 - Liste de commandes importantes
Voici une courte liste des commandes que nous avons utilisée aujourd'hui. Entre
parenthèses, vous trouverez le nom en anglais de la commande (pour vous aider à
retenir la commande). Entre crochets, vous trouverez les options les plus
souvent utilisées&nbsp;:

## 8.1 - Explorer des dossiers
- **`ls`**&nbsp;: Lister les fichiers et les dossiers (list) **`[-l, -h]`**
- **`pwd`**&nbsp;: Afficher le dossier présent (present working directory)
- **`cd`**&nbsp;: Changer de dossier (change directory) **`[. .. ~ - /]`**

## 8.2 - Explorer des fichiers
- **`wc`**&nbsp;: Afficher le nombre de lignes d'un fichier (word count) **`[-l]`**
- **`cat`**&nbsp;: Afficher le contenu d'un fichier (concatenate)
- **`head`**&nbsp;: Afficher le début d'un fichier **`[-n]`**
- **`tail`**&nbsp;: Afficher la fin d'un fichier **`[-n]`**
- **`less`**&nbsp;: Lire un fichier

## 8.3 - Créer, copier et déplacer des fichiers et dossiers
- **`cp`**&nbsp;: Copier des fichiers et dossiers (copy) **`[-r]`**
- **`mv`**&nbsp;: Déplacer ou renommer fichiers et dossiers (move)
- **`rm`**&nbsp;: Effacer des fichiers ou des dossiers (remove) **`[-r, -f]`**
- **`touch`**&nbsp;: Créer (ou mettre à jour) un fichier
- **`mkdir`**&nbsp;: Créer un dossier (make directory)

