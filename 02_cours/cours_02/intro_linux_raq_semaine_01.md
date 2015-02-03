# Introduction à Linux RAQ - Cours 02
\large  
Eric Normandeau - 2015-02-02  
(**Version TRÈS PRÉLIMINAIRE**)
(**Version NON terminée**)

# Plan de cours
1. Dossiers spéciaux [. .. ~ / -]
1. Plus de commandes
1. Plus de sujets
1. Exemple d'analyses
1. Exercices

# Infos pour construire le cours 02

## Autres commandes utiles
- **`history`** : Lister les commandes utilisées
- **`man`** : Lire le manuel d'une commande
- **`echo`** : Afficher du texte à l'écran
- **`clear`** : Vider le terminal (aussi **`Ctrl-L`**)
- **`sleep`** : Attendre pour un lapse de temps (secondes, minutes...)
- **`Ctrl-C`** : Canceller une commande
- **`Ctrl-D`** : Sortir d'un programme ou arrêter le terminal

cd . .. ~ - /
alias (eg: ll)
text file formats (Windows \r\\n, MacOS ^M, Linux \\n)
Sous Linux, la racine absolue du système est **`/`**, appelé *slash*.
grep -c ">" fichier.fasta  # Attention aux guillemets!!!

## Explorer les séquences
Nous allons tester ces mêmes commandes avec le dossier de séquences.
Premièrement, il faut remonter au dossier supérieur **`..`**, trouver le
dossier de séquences et s'y déplacer :

```bash
    cd ..
    ls

    cd 01_sequences
    ls
```

On voit qu'il y a deux fichier des séquences **`sequences_01.fasta`** et
**`sequences_02.fasta`**. On va utiliser les commandes **`wc -l`**, **`head`**,
**`tail`** et **`less`** pour les explorer.

```bash
    wc -l sequences_01.fasta
    wc -l sequences_02.fasta

    # Ou, encore mieux
    wc -l *.fasta  # * veut dire n'importe quelle chaîne de texte

    # Voir le début des fichiers
    head sequences_01.fasta
    head sequences_02.fasta

    # Ou, encore mieux
    head -n 6 *.fasta
```

