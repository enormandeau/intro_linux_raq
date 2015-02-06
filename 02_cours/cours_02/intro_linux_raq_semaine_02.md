# Introduction à Linux RAQ - Cours 02
Eric Normandeau - 2015-02-05  
(**Version NON terminée**)

# Plan de cours
1. Introduction
1. Dossiers importants
1. Commandes utiles
1. Entrées et sorties
1. Pipelines
1. Mot de la fin
1. Exercices
1. Liste de commandes importantes


# 1 - Introduction
Dans ce deuxième cours d'introduction à Linux, nous allons poursuivre notre
exploration des commandes importantes. Je vais de plus en plus considérer que
la matière déjà vue est acquise, mais n'hésitez surtout pas si vous avez besoin
d'un rappel sur une fonction, un paramêtre, une manière de faire les choses,
etc.

Nous allons aussi parler d'entrée standard, de sortie standard et d'erreur
standard (**`standard input`**, **`standard_output`** et **`standard_error`**)
et voir plus d'exemples de redirection de sortie de programmes. Nous verrons
comment rediriger la sortie d'un programme directement dans un autre programme,
ce qu'on appelle un **`pipeline`**, ce qui nous permettra de commencer à
manipuler des fichiers texte.


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
- **`.`** : Dossier dans lequel vous vous trouvez présentement.
- **`..`** : Dossier parent de celui dans lequel vous vousu trouvez.
- **`~`** : Votre dossier d'utilisateur (eg : **`/home/user02`**)
- **`/`** : Le dossier racine du système.
- **`-`** : Le dossier où vous vous trouviez juste précédemment.


# 3 - Commandes utiles
Certaines commandes nous rendent la vie plus facile. Elles ne nous permettent
pas par elles-mêmes d'accomplir des tâches mais font en sorte qu'on peut être
plus efficace et mieux suivre ce qui se passe sur le système. Voici
quelques-unes de ces commandes :

La commande **`history`** liste les commandes qu'on a utilisé dans le passé en
ordre chronologique. Cette commande peut être pratique en combinaison avec la
commande **`grep`** que nous allons aborder plus loin pour trouver des
commandes complexes que nous avons lancées dans le passé. Lancée seule et sans
options, **`history`** n'est pas toujours très pratique si notre historique de
commandes est long.


```bash
    history
```

Une autre façon de trouver des commandes lancées auparavant est d'utiliser la
commande **`Ctrl-R`**, qui lance une recherche à partir des commandes les plus
récentes. Après avoir appuyé sur **`Ctrl-R`**, il suffit de taper un bout de
commande et le terminal cherche en ordre chronologique inverse la première
commande qui correspond au texte cherché. Si le terminal trouve une commande
qui correspond, vous pouvez chercher plus loin dans le temps en appuyant à
nouveau sur **`Ctrl-R`**. Lorsqu'une commande est affichée, vous pouvez la
lancer directement en appuyant sur **`Enter`** ou la modifier en vous déplaçant
dedans avec les flèches à gauche et à droite. Finalement, vous pouvez canceller
la recherche avec **`Ctrl-C`**.

La commande **`Ctrl-C`** vous permet de canceller une commande en cours
d'exécution, alors que la commande **`Ctrl-D`** arrête un programme, incluant
le terminal **`bash`** lui-même. Vous pouvez donc utiliser **`Ctrl-D`** pour
quitter votre session de connexion **`ssh`** au serveur et même pour fermer le
terminal. Sur Mac, il est possible que la fenêtre du terminal ainsi *fermé*
demeure en fait ouverte. Ce comportement peut être modifié dans les options du
terminal.

La commande **`echo`** affiche le texte qu'on lui passe. Avec les bonnes
options, on peut composer des messages à l'écran.

```bash
    echo "Bienvenu au deuxième cours"  # Aucune option
    echo -n "Nous sommes le "; date -I  # Le -n veut dire "no newline"
```

La commande **`man`** sert à consulter le manuel des commandes disponibles. Le
manuel est affiché grâce à la commande **`less`**.

```bash
    man echo  # Cherchez les options -n et -e
```

La commande **`top`** affiche les processus qui utilisent le plus de ressources
sur le système. On peut trier les processus en fonction de leur utilisation de
différentes ressources (mémoire, processeurs, etc.). On peut même limiter
l'affichage à un utilisateur particulier en tapant **`u`** et en entrant le nom
de l'utilisateur. Lancez **`top`** et tentez d'afficher seulement les processus
lancés par votre utilisateur.

```bash
    top
```

La commande **`clear`** permet de vider le terminal et de remettre le curseur
en haut. On peut également utiliser **`Ctrl-L`** pour arriver au même effet.

Finalement, la commande **`sleep`** sert à marquer une pause en secondes, ce
qui peut être utile dans des scripts. On peut également utiliser les options
pour que la pause soit plutôt en minutes, heures, etc. 

```bash
    sleep 3   # Attendre 3 secondes
    sleep 3s  # Identique à la commande précédente
    sleep 3m  # Attendre 3 minutes
    sleep 3h  # Attendre 3 heures
```


# 4 - Entrées et sorties
- **`>`**
- **`>>`**
- **`<`**
- **`2>`**
- **`2>&1`**
- **`tee`**


# 5 - Pipelines
- Use alice.txt and sequences
- Basic for now (ie: grep | wc)
- Mettre exemples de choses qu'on peut faire avec grep/sed/perl...


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

