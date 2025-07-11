# Chapitre 14 : xargs et find

Nous avons découvert `find` au chapitre 8, et eu un aperçu de ses nombreuses
possibilités. Comme tout outil de la tradition Unix, il ne fait qu'une chose,
et le fait bien. Depuis le chapitre 10, nous avons vu qu'il était possible de
"combiner" des commandes en redirigeant la sortie de l'une dans l'autre.
Traiter un ensemble de lignes de texte (comme une liste de fichiers) devient
alors facile et pratique...

## xargs

La commande `xargs` s'utilise presque exclusivement dans le cas où une première
commande a renvoyé de nombreuses lignes et on souhaite construire une commande
par ligne. En effet, cet outil utilise l'entrée standard comme arguments pour
créer et lancer ces commandes.

L'utilisation de `xargs` sera donc en général de la forme `commande | xargs
nouvelle_commande`. Ainsi, pour chaque ligne affichée par `commande` sur la
sortie standard, `xargs` exécutera `nouvelle_commande`, et lui fournira la
ligne en tant qu'entréee standard.

## quelques options utiles `find` : les actions

Un cas de figure très utilisé de `xargs` est d'effectuer des actions sur des
fichiers trouvés via `find`. Dans ces actions classiques, on retrouve entre
autres lister les fichiers pour voir leurs attributs, afficher la liste des
fichiers en les séparant autrement qu'avec un retour à la ligne, ou les effacer
directement.

Par exemple, si on se base sur `find /etc -type f` pour trouver tous les
fichiers de `/etc`, on peut alors ajouter `|xargs ls -l` pour lister chaque
fichier via la commande `ls`. Or, find contient depuis quelques temps une
option `-ls`. Cela donc : `find /etc -type f -ls`.

Plusieurs autres options de `find` permettent de se passer de `xargs` ou d :

* `-delete` évitera d'effectuer un `| xargs rm` (attention, pas d'affichage ni
  de confirmation) ;
* `-print0` remplace le retour à la ligne de l'affichage par un caractère nul,
  ce qui permet de plus facilement traiter la sortie, en particulier si le
  fichier ou son chemin comporte des espaces ;
* `-exec` remplace presque `xargs`, puisqu'il permet d'exécuter une commande
  directement depuis `find` ; par exemple, au lieu de faire `find /etc -type f
  | xargs grep -Hi http`, on peut effectuer `find /etc -type f -exec grep -Hi
  {} \;`.

Les actions viennent se placer en dernière position de la commande `find`.

À noter que certaines anciennes versions de `find` ne contiennent pas toujours
les actions, et que `xargs` peut être utilisé autrement qu'avec find.

## Exercices

GameShell, niveaux 40 et 41.

Note : bien qu'il soit techniquement possible de ne pas utiliser `xargs` pour
le niveau 40, il est recommandé de s'en servir ;-)
