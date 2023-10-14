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
qu'en est-il de la recherche de fichiers en elle-même ? Pour cela, c'est la
commande `find` qu'il faut utiliser. Cette commande très puissante va trouver
pour nous les fichiers et répertoires, et dispose de nombreux filtres pour
cela.

La commande `find` fonctionne comme ceci :

```
$ find <option> <chemin> <filtre>
```

Dans les filtres les plus utilisés, on peut retrouver :

* `-name NAME`, qui filtre sur le nom du fichier, ou `-iname NAME`, qui
  effectue le même filtre en étant insensible à la casse ;
* `-type TYPE` filtre sur le type de fichier ; TYPE peut a de nnombreuses
  valeurs possibles, mais les plus utilisées sont `f` (fichier), `d`
  (répertoire) et `l` (lien symbolique) ;
* `-user USER` filtre sur l'utilisateur propriétaire du fichier, et `-group
  GROUP`  filtre sur le groupe propriétaire  du fichier.

On peut aussi filtrer sur les dates de création, de modification, les
permissions ou même la taille. La commannde `find --help` est bien trop
succinte pour avoir accès à toutes les possibilités, mais il existe une autre
commande dédiée à la documentation et à l'aide, nommée man. Pour voir toutes
les options et filtres de find, on peut alors taper la commande `man find`.

## locate

Si find est très complet (et probablement un peu complexe aussi), la recherche
en direct sur le stockage peut s'avérer, dans certains cas, un peu longue (en
particulier si on remet en perspective qu'il fut une époque où les disques durs
étaient bien moins rapides que les SSD d'aujourd´hui), surtout si find doit
rechercher dans des stockages de plusieurs téra-octets.

Pour faire face à cela, il existe plusieurs logiciels qui indexent le contenu
du stockage local dans une base de données et vont, lors de demandes de
recherche de fichiers, requêter la dite base. Sous Windows, on trouvera
[Windows Search](https://en.wikipedia.org/wiki/Windows_Search), sous macOS il
s'agit de [Spotlight](https://en.wikipedia.org/wiki/Spotlight_(Apple)) et
chaque environnement de bureau graphique libre (Gnome, KDE, etc...) possède le sien.

En ligne de commande, on trouvera la commande `updatedb` pour initialiser ou
mettre à jour une base de données de fichiers, et la commande `locate` pour
rechercher dans cette base. Ces commandes sont fournies par le paquet
"plocate".

## Exercices

GameShell, niveaux 19 à 21.
