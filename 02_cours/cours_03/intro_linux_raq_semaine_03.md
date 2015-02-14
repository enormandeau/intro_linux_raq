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

Intro, parler de :

- Manipulation de texte
- Rechercher et remplacer
- Extraire certaines portions du texte

## 2.1 - sed

La commande **`sed`** (pour *stream editor*) permet d'éditer du texte provenant
de fichiers ou de l'entré standard (**`standard input`**). On peut écrire des
scripts pour **`sed`**, mais nous allons nous contenter de l'utiliser dans le
terminal pour faire des commandes d'une ligne, aussi appelés **`oneliners`**.
Sa syntaxe est la suivante&nbsp;;

```bash
    sed [options] commands [file-to-edit]
```

Typiquement, nous allons utiliser **`sed`** pour&nbsp;:

- Rechercher et remplacer du texte
- Extraire des portions de fichiers
- Effacer des portions de fichiers

## 2.2 - awk

La commande **`awk`** est en fait un puissant langage de programmation pour
manipuler des fichiers et des calculs arithmétiques. Son nom vient des
premières lettres des noms des auteurs (Alfred **A**ho, Peter **W**einberger,
and Brian **K**ernighan). On peut écrire des scripts dans le langage de
**`awk`**, mais comme pour sed, nous allons nous contenter de l'utiliser dans
le terminal pour faire des **`oneliners`**. Sa syntaxe est la suivante&nbsp;;

```bash
    awk 'BEGIN {start_action} {action} END {stop_action}' filename
```

Typiquement, nous allons utiliser **`awk`** pour&nbsp;:

- Rechercher et remplacer du texte
- Extraire des portions de fichiers
- Effacer des portions de fichiers

## 2.3 - perl

Le langage de programmation **`perl`** a été à l'origine inventé pour remplacer
**`grep`**, **`find`**, **`sed`** et **`awk`** par un seul programme.


# 3 - Expressions régulières

# 4 - Compression de fichiers

# 5 - Mot de la fin

## 5.1 - Aujourd'hui, nous avons vu&nbsp;:

- Comment *déplier* des séquences fasta
- Les bases des **`sed`**, **`awk`** et **`perl`**
- Un survol des expressions régulières

TODO : message

## 5.2 - Au prochain cours, nous verrons&nbsp;:

- Les éditeurs de texte dans le terminal
- Écrire des scripts bash / perl / python
- Changer les permissions des fichiers
- Créer des aliases de commandes
- Screen et Tmux

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

