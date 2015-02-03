# Introduction à Linux RAQ - Cours 01
\normalsize
Eric Normandeau - 2015-02-03  

# 0 - Plan de cours
1. Introduction
1. Connexion au serveur Linux
1. Terminal et commandes de base
1. Mot de la fin
1. Exercices
1. Liste de commandes importantes

# 1 - Introduction
## 1.1 - À propos du cours
- Débute le 4 février
- Deux heures par semaine
- De 10h à 12h le mercredi matin
- Semi-magistral avec exercices (apportez votre laptop)
- **N'hésitez pas à poser des questions durant le cours !**
- Donné dans la salle Hydro-Québec à l'Université Laval (Québec)
- Disponible en direct avec Google Hangout à l'UQAR
- Disponible en différé sur
  [YouTube](https://www.youtube.com/user/maroonedmorlock/videos)
- Notes de cours disponibles sur
  [GitHub](https://github.com/enormandeau/intro_linux_raq)
- Utilisateurs Windows doivent télécharger
  [putty.exe](http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe)

## 1.2 - Qu'est-ce que Linux ?
Linux est un système d'exploitation, au même titre que Windows et MacOS. Bien
qu'il soit gratuit, Linux est retrouvé moins souvent que Windows et MacOS sur
les ordinateurs standards. Cependant, dans le monde des ordinateurs très
puissants (serveurs de calcul et super-calculateurs), près de 95% des systèmes
installés sont dérivés de UNIX, dont la grande majorité sont des versions de
Linux (appelées *distributions*). Il existe plusieurs dizaines de versions
différentes de Linux, mais il y en a seulement 4-5 qui sont plus fréquentes et
elles sont très similaires. Afin d'alléger la discussion, je vais parler de
"systèmes UNIX" ou même de "Linux" pour désigner à la fois Linux et MacOSX. Il
faut savoir cependant que bien que ces deux systèmes d'exploitation soient
similaires, ils sont quand même légèrement différents et certains programmes ou
commandes qui fonctionnent avec l'un ne fonctionnent pas nécessairement avec
l'autre.

Les systèmes UNIX descendent du système d'exploitation original UNIX à l'époque
où les seuls ordinateurs se trouvaient dans les université, les gouvernements
et les très grosses compagnies. UNIX fait partie des tous premiers systèmes qui
pouvaient être installés sur des ordinateurs fabriqués par différentes
compagnies. Avant cette époque, chaque compagnie vendait son propre système
d'exploitation et c'était le seul qui pouvait fonctionner sur leurs
ordinateurs. UNIX a donc révolutionné la manière dont des chercheurs dans
différentes universités pouvaient collaborer puisque le code qui fonctionnait
sur une machine UNIX fonctionnait également sur une autre. Cette tradition
s'est poursuivie au fil des années avec les descendants de UNIX, dont Linux est
rapidement devenu le plus populaire après sa création au début des années 90.
Linux est un logiciel libre et on peut obtenir la plupart des versions,
appelées *distributions*, gratuitement. 

## 1.3 - Pourquoi utiliser Linux en biologie ?
Les besoins de la recherche scientifique en général et de la biologie en
particulier s'alignent très bien avec les capacités offertes par les systèmes
UNIX&nbsp;:

- Explorer rapidement des données et des hypothèses
- Reproduire des analyses de façon répétée sur différents jeux de données
- Analyser des données demandant une grande puissance de calcul ou beaucoup de
  mémoire

Les systèmes UNIX fournissent un environnement et des outils qui rendent ces tâches
plus faciles. En utilisant Linux en combinaison avec un ou plusieurs langages
de programmation, on peut plus rapidement explorer ses données, reproduire
rapidement des analyses et lancer des programmes gourmands en ressources de
calcul (nombre de coeurs et quantité de mémoire).

Dans certains domaines de la bioinformatique, on retrouve presque exclusivement
des programmes pour Linux et MacOSX. Par exemple, les programmes pour faire des
alignements de séquences et pour découvrir des marqueurs génétiques (ex&nbsp;:
SNPs) sont majoritairement conçus pour être installés et utilisés sur Linux.
Afin d'avoir accès à ces programmes, il faut donc savoir utiliser des
ordinateurs avec des systèmes UNIX.


\newpage


## 1.4 - Exemples d'analyses
- Assemblage et annotation de génomes
- Alignement de séquences
- Trouver des séquences similaires
- Génotypage d'individus par Séquençage
- Analyse d'expression de gènes (RNA-Seq)
- Analyse de la régulation d'expression

Durant la formation, nous allons tenter de faire de courtes analyses de
séquences d'ADN&nbsp;:

- Compter des séquences
- Nettoyer des fichiers de séquences
- Rechercher des séquences similaires avec **`blast`**
- Assembler des génomes bactériens


# 2 - Connexion au serveur Linux
## 2.1 - Pré-requis
- Sur Linux et MacOSX&nbsp;: ouvrir une fenêtre de terminal.
- Sur Windows, télécharger [putty.exe](http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe),
  et le sauvegarder sur votre bureau.

## 2.2 - Connexion sur Linux ou MacOSX
Afin de se connecter au serveur, nous devons premièrement ouvrir un terminal.
Pour les utilisateurs de MacOSX et Linux, lancez la commande suivante dans le
terminal que vous avez ouvert&nbsp;:


```bash
    ssh <username>@raq.ibis.ulaval.ca
```

Vous devrez remplacer **`<username>`** par le nom d'utilisateur que vous avez
reçu. Lorsque demandé, entrez votre mot de passe. Il est normal que vous ne
voyiez pas d'étoiles ou de cercles apparaître lorsque vous tapez votre mot de
passe.

## 2.3 - Connexion sur Windows
Double-cliquer sur l'exécutable **`putty.exe`** que vous avez sauvegardé sur votre
bureau.

Dans la case **`Host Name (or IP address)`**, tapez le nom du serveur&nbsp;:

```bash
    raq.ibis.ulaval.ca
```

Cliquez sur le bouton **`Open`** en bas. Un terminal s'ouvrira où vous devez
entrer votre nom d'utilisateur (par exemple, **`user_99`**) et appuyer sur la
touche **`Enter`**. Lors de la première connexion, **`putty.exe`** vous
avertira que vous ne connaissez pas le serveur et vous demandera de confirmer
que vous souhaitez poursuivre. Cliquez sur **`Yes`** pour continuer. Le serveur
vous demandera alors de taper votre mot de passe et d'appuyer sur la touche
**`Enter`**. C'est normal si aucun caractère n'apparaît pendant que vous tapez
votre mot de passe. Après avoir appuyé sur la touche **`Enter`**, vous serez
connecté au serveur du cours.

Nous allons maintenant configurer **`putty.exe`** pour que l'affichage soit
plus plaisant. Si vous êtes connectés, tapez **`exit`** dans le terminal puis
appuyez sur **`Enter`**. Relancez **`putty.exe`** au besoin. Cliquez sur
l'onglet **`Appearance`** à gauche. Cliquez sur l'option **`Antialiased`** à
peu près au centre dans la section **`Font Settings`**. Toujours dans la même
section, cliquez sur le bouton **`Change...`** pour modifier la police de
caractères. Choisissez une police qui contient le mot **`Mono`** dedans,
ajustez la taille à 11 ou 12, et appuyez sur **`OK`**. Retournez dans l'onglet
**`Session`** en haut à gauche et entrez le nom du serveur
(**`raq.ibis.ulaval.ca`**) et nommez la session **`RAQ`** (au centre). Cliquez
maintenant sur **`Save`** pour sauvegarder les options que nous venons de
choisir. Vous êtes maintenant prêts à utiliser **`putty.exe`**.


# 3 - Terminal et commandes de base
Si vous avez suivi les étapes décrites à la section 2, vous êtes maintemant
connectés à un serveur Linux et vous regardez un terminal vide avec un curseur
qui attend vos commandes.

Le terminal est une fenêtre interactive où on tape des commandes et où les
résultats peuvent être affichés. Il existe plusieurs types de terminaux, mais
le terminal **`bash`** est de loin le plus fréquent. Nous allons utiliser le
terminal **`bash`** tout au long du cours. Il faut bien comprendre qu'**on ne
peut pas utiliser Linux pour des analyses si on ne comprend pas bien comment
fonctionnent le terminal `bash` et le système**. Notre but ultime reste de
faire de la biologie, mais afin de pouvoir faire certaines de nos analyses sous
Linux ou MacOSX, nous devons bien comprendre les bases du terminal.

Dans cette section, nous allons commencer à apprendre les commandes de base du
terminal. Le terminal **`bash`** est très complet. Il permet de manipuler les
fichiers et les dossiers, installer des programmes, éditer des fichiers de
texte, manipuler du texte, lancer des programmes. Il possède même son propre
language de programmation, dont nous allons seulement survoler les bases les
plus utiles.

## 3.1 - Comment lancer des commandes
Pour lancer une commande, on la tape dans le terminal et on appuie sur
**`Enter`**. Par exemple, pour afficher la date, on peut utiliser la commande
**`date`**&nbsp;:

```bash
    date
```

Pour afficher du texte à l'écran, on utilise la commande **`echo`**&nbsp;:

```bash
    echo "Bienvenue à la formation Linux"
```

## 3.2 - Copier-coller dans le terminal
Si vous souhaitez copier et coller des commandes dans le terminal sous MacOSX et
Linux, il se peut que vous ayez à utiliser des touches différentes de
**`Ctrl-C`** et **`Ctrl-V`**. Par exemple, sur MacOSX, vous aurez peut-être à
utiliser **`Cmd-C`** et **`Cmd-V`**, alors que sur Linux, vous utiliserez
**`Ctrl-Shift-C`** et **`Ctrl-Shift-V`**. 

## 3.3 - Commandes de base
Il existe des commandes de base qui permettent d'explorer et de manipuler des
fichiers et des dossiers. Nous allons commencer à apprendre les plus communes
aujourd'hui. Vous pouvez copier et coller les commandes, mais comme le but est
de les apprendre, **je vous recommande fortement taper les commandes**.

### 3.3.1 - Premiers pas
Une fois connectés, nous voulons savoir où nous sommes. La commande **`pwd`**
(pour *present working directory*) nous indique le chemin (path) où nous nous
trouvons&nbsp;:

```bash
    pwd
```

Nous sommes dans le dossier **`/home/username`** où la partie *username* est
votre nom d'utilisateur.

Pour voir ce qu'il y a dans le dossier, nous utilisons la commande **`ls`**&nbsp;:

```bash
    ls
```

La commande nous indique la présence d'un fichier nommé
**`mot_de_bienvenue.txt`**. Nous allons afficher le message contenu dans le
fichier avec la commande **`cat`**&nbsp;:

```bash
    cat mot_de_bienvenue.txt
```

On peut utiliser la touche **`Tab`** (tabulation) pour compléter
automatiquement les noms de commandes, fichiers et dossiers lorsqu'il n'y a pas
d'ambiguité possible. Testez-le en tapant **`cat mot<tab>`**. Le nom du
fichier devrait se compléter automatiquement. Cette façon d'écrire les noms de
fichiers est préférée car elle sauve du temps et évite des erreurs de frappe.

### 3.3.2 - Importer le matériel du cours 01
Afin de pouvoir tester les autres commandes, nous allons avoir besoin de plus
de dossiers et de fichiers. Nous allons donc copier un dossier déjà préparé
pour le cours 01 avec la commande **`cp`**, que nous allons revoir plus
tard&nbsp;:

```bash
    cd  # Pour retourner dans notre dossier d'utilisateur
    cp -r /cours_intro_linux/cours_01 .
```

Nous pouvons vérifier que le dossier a été copié avec **`ls`**&nbsp;:

```bash
    ls
```

Avec les bonnes options, on pourrait afficher les fichiers et dossiers comme
une liste et voir leur taille. L'option **`-l`** affiche les fichiers en liste
et l'option **`-h`** donne leur taille de façon plus lisible (en Ko, Mo,
Go...)&nbsp;:

```bash
    ls -lh
```

En ajoutant l'option **`-a`** (pour *all*), on pourrait même voir les fichiers
cachés (qui commencent par un point **`.`**). À moins de savoir exactement à
quoi servent ces fichiers cachés, il vaut mieux ne pas les modifier ou les
supprimer.

```bash
    ls -lha
```

Pour se déplacer dans les dossiers, on utilise la commande **`cd`**. Par
exemple, pour aller dans le nouveau dossier **`cours_01`** et lister le contenu
du dossier&nbsp;:

```bash
    cd cours_01
    ls -lh
```

On voit qu'il y a un dossier **`README.txt`**. Pour le lire, on utilise encore
la commande **`cat`**&nbsp;:

```bash
    cat README.txt  # N'oubliez pas d'utiliser <tab>
```

### 3.3.3 - Alice au Pays des Merveilles
Il semble y avoir un dossier qui contient l'histoire d'*Alice au Pays des
Merveilles*. Nous allons donc nous déplacer dans le dossier **`00_alice`** pour
en regarder le contenu &nbsp;:

```bash
    cd 01_alice
    ls
```

On découvre un fichier nommé **`alice.txt`**. Nous allons tenter de le
visualiser en utilisant les commandes **`cat`**, **`head`**, **`tail`** et
**`less`**, mais d'abord, nous allons voir combien de lignes il y a dans ce
fichier&nbsp;: **``**

```bash
    wc -l alice.txt # Nombre de lignes du fichier

    cat alice.txt   # Pas très utile
    head alice.txt  # Voir le début du fichier
    tail alice.txt  # Voir la fin du fichier

    less alice.txt  # Lire tout le fichier
```

Voici quelques commandes utiles lorsqu'on utilise **`less`**&nbsp;:

- **`Arrow down`** (ou **`Ctrl-N`**)&nbsp;: Se déplacer d'une ligne vers le bas.
- **`Arrow up`** (ou **`Ctrl-P`**)&nbsp;: Se déplacer d'une ligne vers le haut.
- **`Spacebar`**&nbsp;: Avancer d'une page dans le fichier.
- **`d`** (down)&nbsp;: Avancer d'une demi-page dans le fichier.
- **`b`** (back)&nbsp;: Reculer d'une demi-page dans le fichier.
- **`g`** (go top)&nbsp;: Retourner au début du fichier.
- **`G`** (Go bottom)&nbsp;: Aller à la fin du fichier.
- **`q`** (quit)&nbsp;: Quitter **`less`**.
- **`/`** (search)&nbsp;: Faire une recherche de texte.
- **`n`** (next found item)&nbsp;: Trouver la prochaine occurence du texte cherché.
- **`N`** (previous found item)&nbsp;: Trouver la précédente occurence du texte cherché.

### 3.3.4 - Jongler avec des fichiers et des dossiers
Nous allons maintenant **créer**, **déplacer**, **renommer **et **effacer **des
fichiers et des dossiers. Pour cela, nous allons nous déplacer dans le dossier
**`~/cours_01/02_fichiers_et_dossiers`**. Chaque fois que vous voyez le symbole
**`~`** dans un chemin de dossier, il fait référence à votre dossier
d'utilisateur dans **`/home/username`**. Par exemple, pour l'utilisateur
**`eric`**, la commande suivante retourne dans **`/home/eric`**, se déplace
dans le dossier **`cours_01/02_fichiers_et_dossiers`** qui s'y trouve et en
liste le contenu&nbsp;:

```bash
    cd ~
    cd cours_01/02_fichiers_et_dossiers
    ls -lh
```

Pour copier des fichiers, on utilise la commande **`cp`** suivie du nom du
fichier à copier et puis du nom du nouveau fichier où le copier. Afin de copier
un dossier, il faut utiliser l'option **`-r`**&nbsp;:

```bash
    cp fichier_01.txt copie_fichier_01.txt
    cp -r dossier_01 copie_dossier_01

    ls -lh
```

Pour déplacer ou renomer des fichiers ou dossiers, on utilise la commande
**`mv`**&nbsp;:

```bash
    mv copie_fichier_01.txt fichier_02.txt
    mv copie_dossier_01 dossier_02

    ls -lh
```

Finalement, pour effacer un fichier ou un dossier, on utilise la commande
**`rm`**. Pour les dossiers, il faut ajouter l'option **`-r`**, comme pour la
commande **`cp`**.

```bash
    rm fichier_02.txt
    rm -r dossier_02

    ls -lh
```

**NOTE IMPORTANTE**&nbsp;: Lorsqu'on utilise la commande **`rm`**, **on ne peut
pas revenir en arrière!** Le(s) fichier(s) ou dossier(s) sont effacés de façon
permanente. On ne peut pas les récupérer dans la poubelle. **On doit donc être
extrèmement prudent en utilisant la commande `rm`!**

Pour créer des fichiers et des dossiers vides, on utilise les commandes
**`touch`** et **`mkdir`**&nbsp;:

```bash
    touch nouveau_fichier.txt
    mkdir nouveau_dossier

    ls -lh
```


# 4 - Mot de la fin

## 4.1 - Aujourd'hui, nous avons vu&nbsp;:

- Comment se connecter à un serveur Linux
- Les bases du terminal **`bash`**
- Comment naviguer dans des dossiers
- Comment afficher et lire des fichiers
- Comment manipuler des fichiers (copier, déplacer, renommer, effacer)

Lors du prochain cours, nous allons poursuivre notre apprentissage des
commandes de base qui nous serviront plus tard à préparer et lancer nos
analyses.

## 4.2 - Questions, suggestions
N'hésitez pas à me poser vos questions durant les cours ou par courriel. Je
vais tenter d'y répondre durant les cours. Je vais aussi prendre vos
suggestions en note pour tenter d'améliorer le cours.


\newpage


# 5 - Exercices

## 5.1 - Connexion
- Se connecter au serveur (**`ssh`**)

## 5.2 - Orientation
- Afficher le dossier présent (commande&nbsp;: **`pwd`**)
- Se déplacer à la racine du système (racine&nbsp;: **`/`**, commande&nbsp;: **`cd`**)
- Afficher le contenu du dossier (commande&nbsp;: **`ls`**)
- Explorer un peu les dossier (commandes&nbsp;: **`cd`**, **`ls`**, **`pwd`**)
- Se déplacer dans le dossier **`/home`** (commande&nbsp;: **`cd`**)
- Afficher le contenu du dossier (commande&nbsp;: **`ls`**)
- Essayer de se déplacer dans le dossier d'un autre utilisateur (commande&nbsp;: **`cd`**)
- Retourner dans votre dossier d'utilisateur  
  (dossier&nbsp;: **`/home/username`**, ou **`~`**, commande&nbsp;: **`cd`**)

## 5.3 - Fichiers
- Effacer le dossier du cours (dossier&nbsp;: **`cours_01`**, commande&nbsp;: **`rm`**)
- Copier à nouveau le dossier du cours dans votre dossier utilisateur  
  (dossier&nbsp;: **`/cours_intro_linux/cours_01`**, commande&nbsp;: **`cp -r`**)
- Se déplacer dans le dossier **`~/cours_01/02_fichiers_et_dossiers`** (commande&nbsp;: **`cd`**)
- Afficher le contenu du fichier **`fichier_01.txt`** (commande&nbsp;: **`cat`**)
- Créer un nouveau fichier nommé **`mon_fichier.txt`** (commande&nbsp;: **`touch`**)
- Faire une copie de ce fichier nommée **`copie_mon_fichier.txt`** (commande&nbsp;: **`cp`**)
- Renommer cette copie en **`fichier_02.txt`** (commande&nbsp;: **`mv`**)
- Effacer ce fichier (**`fichier_02.txt`**, commande&nbsp;: **`rm`**)

## 5.4 - Dossiers
NOTE: Ne pas oublier que certaines commandes nécessitent l'option **`-r`**
quand on manipule des dossiers.

- Copier le fichier **`fichier_01.txt`** dans **`dossier_01`** (commande&nbsp;: **`cp`**)
- Faire une copie de ce dossier appelée **`nouveau_dossier`** (commande&nbsp;: **`cp`**)
- Renommer **`nouveau_dossier`** en  **`dossier_02`** (commande&nbsp;: **`mv`**)
- Afficher le contenu de **`dossier_02`** (commande&nbsp;: **`ls`**)
- Effacer **`dossier_02`** (commande&nbsp;: **`rm`**)


\newpage


## 6 - Liste de commandes importantes
Voici une courte liste des commandes que nous avons utilisée aujourd'hui. Entre
parenthèses, vous trouverez le nom en anglais de la commande (pour vous aider à
retenir la commande). Entre crochets, vous trouverez les options les plus
souvent utilisées&nbsp;:

## 6.1 - Explorer des dossiers
- **`ls`**&nbsp;: Lister les fichiers et les dossiers (list) **`[-l, -h]`**
- **`pwd`**&nbsp;: Afficher le dossier présent (present working directory)
- **`cd`**&nbsp;: Changer de dossier (change directory) **`[. .. ~ - /]`**

## 6.2 - Explorer des fichiers
- **`wc`**&nbsp;: Afficher le nombre de lignes d'un fichier (word count) **`[-l]`**
- **`cat`**&nbsp;: Afficher le contenu d'un fichier (concatenate)
- **`head`**&nbsp;: Afficher le début d'un fichier **`[-n]`**
- **`tail`**&nbsp;: Afficher la fin d'un fichier **`[-n]`**
- **`less`**&nbsp;: Lire un fichier

## 6.3 - Créer, copier et déplacer des fichiers et dossiers
- **`cp`**&nbsp;: Copier des fichiers et dossiers (copy) **`[-r]`**
- **`mv`**&nbsp;: Déplacer ou renommer fichiers et dossiers (move)
- **`rm`**&nbsp;: Effacer des fichiers ou des dossiers (remove) **`[-r, -f]`**
- **`touch`**&nbsp;: Créer (ou mettre à jour) un fichier
- **`mkdir`**&nbsp;: Créer un dossier (make directory)

