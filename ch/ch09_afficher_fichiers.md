# Chapitre 9 : affichage des fichiers

Nous avons vu comment agir sur les fichiers, mais pas comment les afficher.

## cat

La commande `cat` permet d'afficher un ou plusieurs fichiers (c'est une
abréviation de "concatenate"). Pour un fichier c'est assez simple : `cat
FICHIER`. Pour plusieurs fichiers, toujours aussi simple : `cat FICHIER1
FICHIER2 FICHIER3`.

Mais `cat` a un inconvénient majeur : si le contenu du fichier dépasse la
hauteur du terminal, alors les premières lignes ne seront pas visibles à moins
d'utiliser l'ascenceur de l'émulateur de terminal. On peut voir cela avec un
fichier standard du système : `cat /etc/services`.

Autre point d'attention pour `cat` : il fonctionne avec tous les fichiers, ce
qui inclut les binaires. Ceci peut poser des problèmes d'affichage dans le
terminal, qu'on peut résoudre avec la commande `reset`.

Pour aller plus loin avec cat, [une vidéo de Yves Rougy](https://www.youtube.com/watch?v=n0YMUm13p34).

## les pagers

Si on souhaite afficher un fichier texte plus long que la hauteur de l'écran,
on peut utiliser un pager : il va limiter l'affichage à la hauteur de l'écran,
et grâce à une touche spéciale (en général la touche espace) il est possible
d'avancer page par page.

Il existe deux principaux pagers : more et less, dont l'usage est très
similaire. On peut donc plus facilement lire le fichier du sous-chapitre
précédent avec ces outils : `more /etc/services` ou `less /etc/services`.

En dehors des principaux pagers, il existe quelques autres projets plus
récents, comme [most](http://www.jedsoft.org/releases/most/) et
[bat](https://crates.io/crates/bat).

Une étude plus approfondie de chaque pager permet de dévoiler des
fonctionnalités parfois assez confortables, comme de la couleur ou des numéros
de lignes.

## head et tail

On peut aller plus loin dans l'affichage de fichiers, comme vouloir afficher
uniquement les N premières lignes ou les N dernières lignes d'un fichier, voire
même afficher les nouvelles lignes d'un fichier au fur et à mesure qu'elles
apparaissent.

La commande `head FICHIER` affiche les 10 premières lignes d'un fichier
FICHIER, mais il est possible d'agir sur ce nombre avec l'argument `-n`, ainsi
`head -n 20 /etc/services` affichera les 20 premières lignes du fichier
`/etc/services`. 

Il est possible de faire l'inverse avec `tail`, qui affichera les 10 dernières
lignes d'un fichier, et dispose de la même option `-n` que `head`.

Les commandes `head` et `tail` disposent d'une syntaxe  historique, en général
prise en charge par les versions récentes. Pour notre exemple précédent, la
commande `head -20 /etc/services` fonctionnera aussi.

Mais `tail` a plus d'un tour dans son sac : avec l'option `-f`, on peut alors
afficher les nouvelles lignes d'un fichier au fur et à mesure de leur
apparition. Cela est très pratique pour un fichier de log, par exemple de
serveur web, où on peut observver en direct les requêtes arriver.

## Exercices

GameShell, niveaux 22 à 24.
