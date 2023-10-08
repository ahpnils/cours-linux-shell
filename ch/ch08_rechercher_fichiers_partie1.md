# Chapitre 8 : rechercher des fichiers, partie 1

Rechercher des fichiers avec `ls`, `pwd` et `cd` peut s'avérer fastidieux. Il
existe fort heureusement des solutions plus pratiques, et plus complètes.

## Lister des arborescences avec ls et tree

Nous avons vu au chapitre 2 la commande `ls`, qui permet de lister le contenu
d'un répertoire. Elle possède une option `-R`, qui effectue un affichage
récursif. Ainsi, dans le jeu GameShell, il est possible de voir à l'avance
l'arborescence du donjon :

```
[mission 1] $ ls -R Chateau/Donjon/
Chateau/Donjon/:
Premier_etage

Chateau/Donjon/Premier_etage:
Deuxieme_etage

Chateau/Donjon/Premier_etage/Deuxieme_etage:
Haut_du_donjon

Chateau/Donjon/Premier_etage/Deuxieme_etage/Haut_du_donjon:
```

Cela est très pratique, mais avec beaucoup de fichiers cela peut encombrer
l'affichage. La commande `tree` résoud cela :

```
[mission 1] $ tree Chateau/Donjon/
Chateau/Donjon/
└── Premier_etage
    └── Deuxieme_etage
        └── Haut_du_donjon

4 directories, 0 files
```

## find

Les commandes `ls` et `tree` nous offrent un aperçu de notre arborescence, mais
qu'en est-il de la recherche de fichiers en elle-même ? Pour cela, utili

## locate



## Exercices

GameShell, niveaux 19 à 21.
