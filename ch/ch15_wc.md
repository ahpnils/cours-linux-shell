# Chapitre 15 : compter les mots et lignes

Encore un outil utilisé quasi-exclusivement avec des redirections
d'entrées-sorties !

## wc (word count)

La commande `wc` compte les mots, les caractères mais aussi les lignes. 
La commande `wc` compte les lignes, les mots et les octets d'une fichier. Un
mot est une séquence de caractères affichables délimité par un espace.

On peut donner en option un ou plusieurs fichiers (et le total sera alors 
affiché en dernière ligne), mais il est aussi possible de compter à
partir de l'entrée standard. On peut donc faire `commande | wc`.

Quelques options :

* `-l` compte uniquement les lignes ;
* `-m` compte uniquement le nombre de caractères ;
* `-w` compte uniquement le nombre de mots ;
* `-c` compte uniquement le nombre d'octets.

Quelques exemples :

* compter le nombre de lignes d'un fichier `wc -l /etc/services` ;
* compter le nombre de fois que le mot "http" apparait dans /etc/services : `grep http /etc/services | wc -w`.

## Exercices

GameShell, niveaux 42 et 43.
