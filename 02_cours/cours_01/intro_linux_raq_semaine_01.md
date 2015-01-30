# Introduction à Linux RAQ - Cours 01
\large  
Eric Normandeau - 2015-01-29

# Plan de cours
1. Introduction
1. Connection au serveur Linux
1. Le terminal

# 1 - Introduction
## 1.1 - Qu'est-ce que Linux ?

Linux est un système d'exploitation, au même titre que Windows et MacOSX. Bien
qu'il soit gratuit, Linux est beaucoup moins fréquemment retrouvé sur les
ordinateurs standards (tours et ordinateurs portables). Cependant, dans le
monde des ordinateurs très puissants (serveurs de calcul et
super-calculateurs), près de 95% des systèmes installés sont dérivés de UNIX,
dont la grand majorité sont des versions de Linux. Il existe plusieurs dizaines
de versions différentes de Linux, mais il y en a seulement 4-5 qui sont plus
fréquentes et elles sont très similaires. Afin d'alléger la discussion, je vals
parler de "systèmes UNIX" ou même de "Linux" pour désigner à la fois Linux et
MacOSX. Il faut savoir cependant que bien que ces deux systèmes d'exploitation
soient similaires, ils sont quand même légèrement différents et certains
programmes ou commandes qui fonctionnent avec l'un pourraient ne pas
fonctionner avec l'autre.

Les systèmes UNIX descendent du système d'exploitation origal UNIX à l'époque
où les seuls ordinateurs se trouvaient dans les université, les gouvernements
et les très grosses compagniew. UNIX fait partie des tous premiers systèmes qui
pouvaient être installés sur des ordinateurs fabriqués par différentes
compagines. Avant cette époque, chaque compagine vendait son propre système
d'exploitation et c'était le seul qui pouvait fonctionner sur leurs
ordinateurs. UNIX a donc révolutionné la manière dont des chercheurs dans
différentes universités pouvaient collaborer puisque le code qui fonctionnait
sur une machine UNIX fonctionnait également sur une autre. Cette tradition
s'est poursuivie au fil des années avec les descendants de UNIX, dont Linux est
rapidement devenu le plus populaire après sa création au début des années 90.

## 1.2 - Pourquoi utiliser Linux en biologie ?

Les besoins de la recherche scientifique, qui s'appliquent également à la
biologie, s'allignent très bien avec les capacités offertes par les systèmes
UNIX :

- Explorer rapidement des données et des hypothèses
- Reproduire des analyses de façon répétée sur différents jeux de données
- Analyser des données demandant une grand puissance de calcul ou beaucoup de mémoire

Les systèmes UNIX fournissent un environnement et des outils rendent ces tâches
plus faciles. En utilisant Linux en combinaison avec un ou plusieurs langages
de programmation, on peut plus rapidement explorer ses données, reproduire
rapidement des analyses et lancer des programmes gourmands en ressources de
calcul (nombre de coeurs et quantité de mémoire).

Dans certains domaines de la bioinformatique, on retrouve presqu'exclusivement
des programmes pour Linux et MacOSX. Par exemple, la plupart des programmes
pour faire des alignements de séquences et découvrir des SNPs sont conçus pour
être installés et utilisés sur Linux. Afin d'avoir accès à ces programmes, il
faut donc savoir utiliser des ordinateurs avec des systèmes UNIX.

## 1.3 - Examples d'analyses

- Alignement de séquences
- Assemblage de génomes de novo
- Génotypage par Séquençage

- (... autre chose que génomique)

\newpage

# 2 - Connection au serveur Linux

## 2.1 Pré-requis

- Sur Linux et MacOSX: ouvrir une fenêtre de terminal.
- Sur Windows, télécharger [putty.exe](http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe),
  sauvegarder sur votre bureau.

## 2.2 Connexion sour Linux ou MacOSX

Afin de se connecter au serveur, nous devons premièrement ouvrir un terminal.
Pour les utilisateurs de MacOSX et Linux, lancez la commande suivante dans le
terminal que vous avez ouvert:


```bash
    ssh <username>@raq.ibis.ulaval.ca
```

Vous devez remplacer **`<username>`** par le nom d'utilisateur que vous avez reçu.
Lorsque demandé, entrez votre mot de passe. Il est normal que vous ne voyez pas
d'étoiles ou de cercles apparaître lorsque vous tapez votre mot de passe.

## 2.3 Connexion sour Windows

Double-cliquer sur l'exécutable **`putty.exe`** que vous avez sauvegardé sur votre
bureau.

Dans la case **`Host Name (or IP address)`**, tapez le nom du serveur :

```
    raq.ibis.ulaval.ca
```

Cliquez sur le bouton **`Open`** en bas. Un terminal s'ouvrira où vous devrez
entrer votre nom d'utilisateur (par exemple, **`user_99`**) et appuyer sur la
touche **`Enter`**. Le serveur répondra en vous demandant de taper votre mot de
passe et d'appuyer sur la touche **`Enter`**. C'est normal si aucun caractère
n'apparaît pendant que vous tapez votre mot de passe. Après avoir appuyé
sur la touche **`Enter`**, vous serez connecté au serveur du cours.

\newpage

# 3 - Le terminal

Si vous avez suivi les étapes décrites à la section 2, vous êtes maintemant
connecté à un serveur Linux et vous regardez un terminal vide avec un curseur
qui attend vos commandes.

Le terminal est une fenêtre interactive où on tape des commandes et où les
résultats peuvent être affichés. Il existe plusieurs types de terminaux, mais
le terminal **`bash`** est de loin le plus fréquent. Nous allons utiliser le
terminal **`bash`** tout au long du cours. Il faut bien comprendre qu'**on ne peut
pas utiliser Linux pour des analyses si on ne comprend pas bien comment le
terminal `bash` et le système fonctionnent**. Notre but ultime reste de
faire de la biologie, mais afin de pouvoir faire certaines de nos analyses sous
Linux ou MacOSX, nous devons bien comprendre les bases du terminal.

Dans cette section, nous allons commencer à apprendre les commandes de base du
terminal. Le terminal **`bash`** est très complet. Il permet de manipuler fichiers
et dossier, installer des programmes, éditer des fichiers de texte, manipuler
du texte, lancer des programmes. Il possède même son propre language de
programmation, dont nous allons seulement survoler les bases les plus utiles.

## Commandes de base

Pour utiliser une commande, on la tape dans le terminal et on appui sur
**`Enter`**. Par exemple, pour afficher la date, on peut utiliser la commande
**`date`** :

```
    date
```

Nous allons maintenant copier le contenu d'un dossier prédéfini

Afin d'explorer 

## Cette semaine

- date
- echo
- clear (Ctrl-L)
- pwd
- ls
- cd
- mkdir
- touch
- Ctrl-C
- history (up arrow)

- mv
- cp
- rm

- > (write to file)
- >> (append to file)
- < (input)

- cat

## Futur

- passwd
- head
- tail
- less
- wc



- grep



- chmod
- chown

