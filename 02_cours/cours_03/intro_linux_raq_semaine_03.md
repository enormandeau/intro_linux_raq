# Introduction à Linux RAQ - Cours 02
Eric Normandeau - 2015-02-13

# Plan de cours

1. Introduction
1. sed, awk et perl
1. Expressions régulières
1. Compression de fichier
1. Mot de la fin
1. Exercices
1. Liste de commandes importantes


# 1 - Introduction

# 1.1 - Retour sur les exercices

Réponse aux questions relatives aux exercices de la semaine passée.

# 1.2 - Retour sur question avec séquences fasta

Nous souhaitons trouver toutes les séquences qui débutent par **`ATG`** dans le
fichier **`sequences_wrapped.fasta`**. Nous utilisons la commande **`grep`**.


```bash
    # Séquences avec ATG au début de la ligne
    grep -E "^ATG" sequences_wrapped.fasta
```

Malheureusement, les séquences sont repliées sur plusieurs lignes. Nous allons
devoir les formatter pour que chaque séquence soit sur une seule ligne.

```bash
    # Déplier les séquences (une ligne par séquence)
    fasta_unwrap.py sequences_wrapped.fasta sequences_unwrapped.fasta
```

Nous sommes maintenant prêts à trouver les séquences qui débutent par
**`ATG`**.

```bash
    # Séquences qui débutent par ATG
    grep -E "^ATG" sequences_unwrapped.fasta
```

Finalement, nous allons retrouver le nom de ces séquences.

```bash
    # Trouver le nom des séquences
    grep -B 1 -E "^ATG" sequences_unwrapped.fasta 
    grep -B 1 -E "^ATG" sequences_unwrapped.fasta | grep ">"
    grep -B 1 -E "^ATG" sequences_unwrapped.fasta | grep ">" | cut -c 2-
```

# 1.2 - Importer le matériel du cours 03

Nous allons copier un dossier déjà préparé pour le cours 03 avec la commande
**`cp`**, que nous allons revoir plus tard&nbsp;:

```bash
    cd  # Pour retourner dans notre dossier d'utilisateur
    cp -r /cours_intro_linux/cours_03 .
```

Toutes les commandes du cours utilisant des fichiers sont lancées à partir du
dossier **`/home/username/cours_03/01_fichiers`**.


# 2 - sed, awk et perl

# 3 - Expressions régulières

# 4 - Compression de fichiers

# 5 - Mot de la fin

## 5.1 - Aujourd'hui, nous avons vu&nbsp;:

- asdf
- asdf
- asdf

message

## 5.2 - Au prochain cours, nous verrons&nbsp;:

- asdf
- asdf
- asdf

## 5.3 - Questions et suggestions

N'hésitez pas à me poser vos questions durant les cours ou par courriel. Je
vais tenter d'y répondre durant les cours. Je vais aussi prendre vos
suggestions en note pour tenter d'améliorer le cours.


\newpage


# 6 - Exercices

## 6.1 - sed

- Exercice (commande&nbsp;: **`cmd`**)


\newpage


# 8 - Liste de commandes importantes

Voici une courte liste des commandes que nous avons utilisée aujourd'hui. Entre
parenthèses, vous trouverez le nom en anglais de la commande (pour vous aider à
retenir la commande). Entre crochets, vous trouverez les options les plus
souvent utilisées&nbsp;:

## 8.1 - ASDF

- **`cmd`**&nbsp;: Afficher historique des commandes **`[options]`**

