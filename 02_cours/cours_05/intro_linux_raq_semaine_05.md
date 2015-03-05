# Introduction à Linux RAQ - Cours 05
Eric Normandeau - 2015-03-03


# Plan de cours

1. Introduction
1. Transfers et télécharger
1. Installation de programmes
1. Recherche de séquences similaires avec Blast
1. Boucles et trucs bash
1. Mot de la fin
1. Exercices
1. Liste de commandes importantes


# 1 - Introduction

## 1.1 - Annonces

Il s'agit de l'avant dernier cours.

## 1.2 - Retour sur les exercices

Réponse aux questions relatives aux exercices de la semaine passée.

### Créer fichier haiku

- Taper le texte suivant dans **`haiku.txt`** 

```
    Chaque fleur qui tombe
    Fait vieillir d'avantage
    Les branches du prunier

    - Yosa Buson (1716 - 1783)
```

### Écrire script bash

- **`print_haiku.sh <nom> <fichier>`**
- Imprime **`Bonjour <nom>, voici un haiku:`**
- Imprime ensuite le poême
- Rendre exécutable
- Installer dans dossier **`~/programmes`**

### Créer alias

- Créer un alias **`haiku`** dans **`~/.bashrc`**
- Utilise **`print_haiku.sh`** et variable $USER
- Source **`~/.bashrc`**
- Tester l'alias

## 1.3 - Importer le matériel du cours 05

Nous allons copier un dossier déjà préparé pour le cours 05 avec la commande
**`cp`**, que nous allons revoir plus tard&nbsp;:

```bash
    cd  # Pour retourner dans notre dossier d'utilisateur
    cp -r /cours_intro_linux/cours_05 .
```

Toutes les commandes du cours utilisant des fichiers sont lancées à partir du
dossier **`/home/username/cours_05/`**.


\newpage


# 2 - Transfers et télécharger

## TODO
- Créer fichier avec urls intéressants

Il existe deux commandes principales pour transférer des données entre des
ordinateurs Unix&nbsp;**`scp`** et **`rsync`**. Les deux s'utilisent de façon
similaire à la commande **`cp`**. Les commandes **`wget`** et **`curl`**
servent à télécharger des données à partir d'internet.

## 2.1 - scp
- From To
- form here to server1
- from server1 to here
- from server1 to server2

## 2.2 - rsync
- From To
- form here to server1
- from server1 to here
- from server1 to server2


\newpage


# 3 - Installation de programmes

Nous allons maintenant chacun installer la suite d'outils **`blastplus`** de
NCBI. La procédure est similaire à ce que nous avons déjà fait pour installer
nos scripts.

## 3.1 - Télécharger
- Utiliser **`wget`**

## 3.2 - Décompresser
- tar xvfz (ou B?)

## 3.3 - Compiler
- ./configure; make; make install

## 3.4 - Installer
- make install (si --prefix=/home/$USER/programmes)
- modify path in ~/.profile (si installé manuellement)

## 3.5 - Vérifier l'installation
- blastn -h
- which blastn


\newpage


# 4 - Recherche de séquences similaires avec Blast

## 4.1 - Créer une base de données
- makeblastdb

## 4.2 - Lancer une recherche
- blastn (blastx...)

## 4.3 - Formats de sortie
- formats 0 et 6
- column -t


\newpage


# 5 - Boucles et trucs bash

## 5.1 - Boucle for
- for i in 1 2 3; do echo $i; done

## 5.2 - Boucle while
- cat $file | while read i; do echo $i; done

## 5.3 Utiliser la sortie d'une commande
- `cmd` and $(cmd)


\newpage


# 6 - Mot de la fin

## 6.1 - Aujourd'hui, nous avons vu&nbsp;:

- Transfers et télécharger des fichiers et dossiers
- Installer des programmes
- Rechercher de séquences similaires avec Blast
- Boucles et trucs bash

Description

## 6.2 - Au prochain cours, nous verrons&nbsp;:

- Est-ce qu'il y aura un prochain cours ?

## 6.3 - Questions et suggestions

N'hésitez pas à me poser vos questions durant les cours ou par courriel. Je
vais tenter d'y répondre durant les cours. Je vais aussi prendre vos
suggestions en note pour tenter d'améliorer le cours.


\newpage


# 7 - Exercices

## 7.1 - Blah

- Blah


\newpage


# 8 - Liste de commandes importantes

Voici une courte liste des commandes que nous avons utilisée aujourd'hui. Entre
parenthèses, vous trouverez le nom en anglais de la commande (pour vous aider à
retenir la commande). Entre crochets, vous trouverez les options les plus
souvent utilisées&nbsp;:

## 8.1 - blah

- **`cmd`**&nbsp;: Description. **`[options]`**

