# Introduction à Linux RAQ - Cours 04
Eric Normandeau - 2015-02-20


# Plan de cours

1. Introduction
1. Éditeurs de texte
1. Écrire des scripts
1. Fichiers de configuration
1. Screen et Tmux
1. Mot de la fin
1. Exercices
1. Liste de commandes importantes


# 1 - Introduction

## 1.1 - Retour sur les exercices

Réponse aux questions relatives aux exercices de la semaine passée.


## 1.2 - Importer le matériel du cours 04

Nous allons copier un dossier déjà préparé pour le cours 04 avec la commande
**`cp`**, que nous allons revoir plus tard&nbsp;:

```bash
    cd  # Pour retourner dans notre dossier d'utilisateur
    cp -r /cours_intro_linux/cours_04 .
```

Toutes les commandes du cours utilisant des fichiers sont lancées à partir du
dossier **`/home/username/cours_04/01_fichiers`**.


\newpage


# 2 - Éditeurs de texte

Il est utile de savoir utiliser au moins un éditeur de texte qu'on peut
utiliser dans le terminal. Cela permet d'écrire ou d'éditer des scripts et des
fichiers de configuration sur les serveurs où nous travaillons. Il existe des
éditeurs de texte faciles à apprendre, tels **`nano`** et **`joe`**. Nous
allons nous concentrer sur ces deux éditeurs. D'autres éditeurs, comme
**`vim`** et **`emacs`**, sont beaucoup plus difficiles à apprendre mais sont
également beaucoup plus puissants. Nous n'allons pas les voir durant le cours.

## 2.1 - nano

- Créer un nouveau fichier
- Ouvrir un fichier
- Écrire
- Sauvegarder et sortir

## 2.2 - joe

- Créer un nouveau fichier
- Ouvrir un fichier
- Écrire
- Sauvegarder et sortir


\newpage


# 3 - Écrire des scripts

Un script est un ensemble de commandes ou instructions dans un langage
spécifique qui peuvent être lues par un interpréteur pour accomplir des tâches.
Par exemple, un script **`bash`** contient une suite de commandes qui seront
exécutées par l'interpréteur **`bash`**. Dans cette section, nous allons voir
comment écrire et exécuter des scripts **`bash`**. Nous allons aussi voir
comment nous pouvons *`installer`* nos scripts pour pouvoir les utiliser comme
les autres commandes.

- count_fasta_sequences.sh
- Écrire la commande de base
- bash count_fasta_sequences.sh file
- Ajouter des commentaires
- Script incluant $1
- Shebang! et chemin (./ ou /home/user11/...)
- chmod u+x
- Ajouter ~/bin courant au PATH
- Y copier le script
- Lancer le script
- Exemple de script python pour montrer que c'est pareil

Au fil du temps, on installe des programmes et on écrit des scripts qui nous
sont utiles. Il devient alors plus rapide et facile de faire les analyses
souhaitées.


\newpage


# 4 - Fichiers de configuration

Lorsqu'on se connecte à un serveur Linux ou qu'on ouvre un terminal sur Linux
ou MacOS, le système lit des fichiers de configuration. Ces fichiers
définissent des options par défaut pour les commandes, les dossiers où chercher
des programmes et des aliases qui peuvent être utilisés dans le terminal. On
peut éditer ces fichiers (**`prudemment`**) pour modifier les options, ajouter
des dossiers de programmes et des aliases. Il est plus prudent cependant de
créer des fichiers supplémentaires que nous allons modifier et charger à partir
des fichiers standards.

- .bashrc
- .profile
- Créer .bash_path et .bash_aliases


\newpage


# 5 - Screen et tmux

On travaille habituellement de façon interactive dans le terminal. Il faut
l'ouvrir et lancer des commandes, puis attendre que les commandes se terminent
avant de pouvoir faire autre chose. Cette façon de faire est la plus simple
mais ne suffit pas toujours. Parfois, il faudrait se déconnecter d'un serveur
tout en laissant nos tâches continuer à tourner. Les programmes **`screen`** et
**`tmus`** ont été créés justement pour répondre à ce besoin. Nous allons nous
concentrer sur **`screen`** car il est installé par défaut sur la plupart des
systèmes Linux mais **`tmux`**, son cousin plus jeune, gagne en popularité.

- screen / exit
- screen Ctrl-A D
- screen -list
- screen -r
- Autres options (nom de session, créer fenêtres et panes)


\newpage


# 6 - Mot de la fin

## 6.1 - Aujourd'hui, nous avons vu&nbsp;:

- Éditer fichiers textes
- Écrire et lancer scripts
- Fichiers de configuration
- Utiliser screen

Nous avons à présent vu la grande majorité des commandes et options qui sont
utilisées fréquemment. Nous avons même survolé **`perl`** et les expressions
régulières. Avec ces outils, nous pouvons préparer et lancer des analyses
simples.

## 6.2 - Au prochain cours, nous verrons&nbsp;:

- Les éditeurs de texte dans le terminal
- Écrire des scripts bash / perl / python
- Changer les permissions des fichiers
- Créer des alias de commandes
- screen et tmux

## 6.3 - Questions et suggestions

N'hésitez pas à me poser vos questions durant les cours ou par courriel. Je
vais tenter d'y répondre durant les cours. Je vais aussi prendre vos
suggestions en note pour tenter d'améliorer le cours.


\newpage


# 7 - Exercices

## 7.1 - asdf

- asdf (commande&nbsp;: **`cmd`**)


\newpage


# 8 - Liste de commandes importantes

Voici une courte liste des commandes que nous avons utilisée aujourd'hui. Entre
parenthèses, vous trouverez le nom en anglais de la commande (pour vous aider à
retenir la commande). Entre crochets, vous trouverez les options les plus
souvent utilisées&nbsp;:

## 8.1 - sed, awk et perl

- **`cmd`**&nbsp;: Description **`[options]`**

