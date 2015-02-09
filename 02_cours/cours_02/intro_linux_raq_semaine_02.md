# Introduction à Linux RAQ - Cours 02
Eric Normandeau - 2015-02-05  
(**Version NON terminée**)

# Plan de cours

1. Introduction
1. Dossiers importants
1. Commandes utiles
1. Entrées et sorties
1. Manipulation de texte
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

# 1.1 - Retour sur les exercies

Réponse aux questions relatives aux exercices de la semaine passée.


# 2 - Dossiers importants

Voici un très court résumé des dossiers spéciaux que nous avons déjà vu et des
dossiers système.

## 2.1 - Dossiers spéciaux

- **`.`** : Dossier dans lequel vous vous trouvez présentement.
- **`..`** : Dossier parent de celui dans lequel vous vousu trouvez.
- **`~`** : Votre dossier d'utilisateur (eg : **`/home/user02`**)
- **`/`** : Le dossier racine du système.
- **`-`** : Le dossier où vous vous trouviez juste précédemment.

## 2.2 - Dossiers systèmes

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


# 3 - Commandes utiles

Certaines commandes nous rendent la vie plus facile. Elles ne nous permettent
pas par elles-mêmes d'accomplir des tâches mais font en sorte qu'on peut être
plus efficace et mieux suivre ce qui se passe sur le système. Voici
quelques-unes de ces commandes :

## 3.1 - La commande history

La commande **`history`** liste les commandes qu'on a utilisé dans le passé en
ordre chronologique. Cette commande peut être pratique en combinaison avec la
commande **`grep`** que nous allons aborder plus loin pour trouver des
commandes complexes que nous avons lancées dans le passé. Lancée seule et sans
options, **`history`** n'est pas toujours très pratique si notre historique de
commandes est long.


```bash
    history
```

## 3.2 - La commande Ctrl-R

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

## 3.3 - La commande Ctrl-C

La commande **`Ctrl-C`** vous permet de canceller une commande en cours
d'exécution, alors que la commande **`Ctrl-D`** arrête un programme, incluant
le terminal **`bash`** lui-même. Vous pouvez donc utiliser **`Ctrl-D`** pour
quitter votre session de connexion **`ssh`** au serveur et même pour fermer le
terminal. Sur Mac, il est possible que la fenêtre du terminal ainsi *fermé*
demeure en fait ouverte. Ce comportement peut être modifié dans les options du
terminal.

## 3.4 - La commande echo

La commande **`echo`** affiche le texte qu'on lui passe. Avec les bonnes
options, on peut composer des messages à l'écran.

```bash
    echo "Bienvenu au deuxième cours"  # Aucune option
    echo -n "Nous sommes le "; date -I  # Le -n veut dire "no newline"
```

## 3.4 - La commande man

La commande **`man`** sert à consulter le manuel des commandes disponibles. Le
manuel est affiché grâce à la commande **`less`**.

```bash
    man echo  # Cherchez les options -n et -e
```

## 3.5 - La commande top

La commande **`top`** affiche les processus qui utilisent le plus de ressources
sur le système. On peut trier les processus en fonction de leur utilisation de
différentes ressources (mémoire, processeurs, etc.). On peut même limiter
l'affichage à un utilisateur particulier en tapant **`u`** et en entrant le nom
de l'utilisateur. Lancez **`top`** et tentez d'afficher seulement les processus
lancés par votre utilisateur.

```bash
    top
```

Pour sortir de la commande **`top`**, vous pressez la touche **`q`**, commme
pour sortir de la commane **`less`**.

## 3.6 - La commande clear

La commande **`clear`** permet de vider le terminal et de remettre le curseur
en haut. On peut également utiliser **`Ctrl-L`** pour arriver au même effet.

## 3.7 - La commande sleep

Finalement, la commande **`sleep`** sert à marquer une pause en secondes, ce
qui peut être utile dans des scripts. On peut également utiliser les options
pour que la pause soit plutôt en minutes, heures, etc. 

```bash
    sleep 3   # Attendre 3 secondes
    sleep 3s  # Identique à la commande précédente
    sleep 3m  # Attendre 3 minutes
    sleep 3h  # Attendre 3 heures

    sleep 3; echo "Hello"
```


# 4 - Entrées et sorties

## 4.1 - Sortie standard (standard output)

Il y a différents types d'entrées et de sorties dans le terminal. Par exemple,
le résultat de plusieurs commandes est affiché directement dans le terminal. On
appelle cette sortie la sortie standard (**`standard output`**). Nous pouvons
décider de rediriger le **`standard output`** dans un fichier en utilisant le
symbole **`>`**.

```bash
    echo "Texte de sortie standard"  # Affiché à l'écran
    echo "Texte de sortie standard" > echo_output.temp  # Redirigé dans fichier

    cat echo_output.temp
```

Il faut noter que si on utilise le symbole **`>`**, le fichier dans lequel nous
redirigeons la sortie sera créé au besoin. Par contre, si il existe déjà, **son
contenu sera remplacé&nbsp;!**. Il faut donc être prudent quand nous utilisons
la redirection vers un fichier.

Si nous souhaitons plutôt *ajouter* la sortie à la fin d'un fichier existant,
nous pouvons utiliser le double symbole **`>>`**. Encore une fois, le fichier
sera créé au besoin mais si il est déjà présent, la sortie standard sera
ajoutée à la fin du fichier.

```bash
    echo "Date:" > la_date.temp  # Un seul '>' pour vider le fichier
    date >> la_date.temp
    echo "..." >> la_date.temp
    echo "La date 3 secondes plus tard" >> la_date.temp
    sleep 3; date >> la_date.temp

    cat la_date.temp
```


## 4.2 - Erreur standard (standard error)

Afin de différencier les sorties de programmes et les messages d'erreurs, ces
derniers sont envoyés vers l'erreur standard (**`standard error`**). Par
exemple, si on lance la commande **`cat`** avec un nom de fichier inexistant,
on obtient une erreur. Il est parfois difficile de différencier les sorties
standards (**`standard output`**) et les erreurs standards (**`standard
error`**) cat elles sont toutes deux affichées à l'écran. Cependant, l'erreur
standard peut être redirigée en utilisant un autre symbole&nbsp;: **`2>`**.

```bash
    cat la_date.temp  # Pas d'erreur = sortie standard
    cat inexistant.temp  # Erreur = erreur standard
```

Nous allons essayer de différencier la sortie standard et l'erreur standard en
les redirigeant dans deux fichiers différents.

```bash
    cat la_date.temp > output.temp 2> error.temp
    echo -e "\n==> Begin Output"; cat output.temp; echo -e "==> End Output\n"
    echo -e "\n==> Begin Error"; cat error.temp; echo -e "==> End Error\n"
```

Cette fois-ci, nous allons donner à la commande **`cat`** un nom de fichier qui
n'existe pas pour voir ce qui arrive avec la sortie et l'erreur standard.

```bash
    cat inexistant.temp > output.temp 2> error.temp
    echo -e "\n==> Begin Output"; cat output.temp; echo -e "==> End Output\n"
    echo -e "\n==> Begin Error"; cat error.temp; echo -e "==> End Error\n"
```

Finalement, pour rediriger à la fois la sortie standard et l'erreur standard,
nous devons utiliser **`&>`** pour rediriger vers un fichier et **`2>&1`** pour
traiter l'erreur standard comme de la sortie standard. Ce dernier truc nous
servira dans la section 4.4 qui porte sur les pipelines.

## 4.3 - Entrée standard (standard input)

On peut passer l'entrée standard (**`standard input`**) à une commande en lui
donnant un nom de fichier mais également en utilisant le symbole **`<`**. Cette
méthode n'est pas utilisée souvent.

```bash
    cat < la_date.temp
```

## 4.4 - Pipelines

Les pipelines sont une des formes de redirection les plus importantes. On
construit un pipeline en utilisant le symbole **`|`** (appelé *pipe* et
prononcé comme en anglais). Le pipeline permet de passer la sortie standard
d'une commande directement dans l'entrée standard de la commande suivante. De
cette façon, on peut traiter la sortie d'une commande avec un ou plusieurs
autres commandes sans avoir à écrire le résultat dans un fichier intermédiaire.
Les pipelines seront particulièrement utiles lorsque nous allons extraire ou de
reformater l'information contenue dans des fichiers texte.

Voici un exemple très simple de pipeline avec seulement deux commandes. Nous
allons compter le nombre de fois où on retrouve le mot **`Alice`** dans le
fichier **`alice.txt`** avec les commandes **`grep`** et **`wc`**&nbsp;:

```bash
    # Dans le dossier contenant le fichier 'alice.txt'
    grep -o Alice alice.txt | wc -l
```

La première commande extrait toutes les occurences du pattron de recherche (ici
c'est simplement 'Alice') et les met une par ligne. Cette sortie est alors
directement passée à la commande suivante comme s'il s'agissait d'un fichier
contenant du texte et celle-ci nous retourne le nombre de lignes. Cette même
formule peut être utilisée pour différentes applications. Par exemple, nous
pourrions être intéressé à savoir combien de fois la séquence **`ACTG`** se
retrouve dans un fichier de séquences.

```bash
    # Dans le dossier contenant le fichier 'sequences.fasta'
    grep -o ACTG sequences_01.txt | wc -l
```

En variant un peu cette recette, on peut répondre rapidement à des questions
plus intéressantes à propos de nos jeux de données, même si ils sont contenus
dans de très gros fichiers.


# 5 - Manipulation de texte

- Nouvelles commandes
  - grep (Regex)
  - sort
  - uniq -c
  - wc
  - perl
  - sed
  - awk
- Donner exemples de de qu'on peut faire avec grep/sed/perl...


# 6 - Mot de la fin

## 6.1 - Aujourd'hui, nous avons vu&nbsp;:

- Révision rapide des dossiers importants
- Quelques commandes utiles
- Les entrées et sorties et la redirection
- Les pipelines
- Quelques commandes pour manipuler du texte
- Une introduction aux expressions régulières (Regex)

## 6.2 - Au prochain cours, nous verrons&nbsp;:

- Manipulation de texte plus avancée
  - Expressions régulières plus en détail
  - Plus de magie avec perl, sed et awk
- Compression et décompression de fichiers

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

## 8.1 - Commandes utiles

- **`cmd`**&nbsp;: Description (english name) **`[options]`**

## 8.2 - Entrées et sorties

## 8.3 - Manipuler du texte

- **`wc`**&nbsp;: Afficher le nombre de lignes d'un fichier (word count)
  **`[-l]`**
- **`cat`**&nbsp;: Afficher le contenu d'un fichier (concatenate)
- **`head`**&nbsp;: Afficher le début d'un fichier **`[-n]`**
- **`tail`**&nbsp;: Afficher la fin d'un fichier **`[-n]`**
- **`less`**&nbsp;: Lire un fichier

