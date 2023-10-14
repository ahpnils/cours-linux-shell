# Chapitre 10 : redirection de sortie dans un programme

Beaucoup de commandes affichent du texte en sortie sur l'affichage. Il est
possible de renvoyer cette sortie vers des programmes qui utilisent du texte en
enntrée.

## les tubes, ou pipes "|"

Le caractère "|" permet de rediriger la sortie d'un programme vers l'entrée
d'un autre. On écrira alors quelque chose de la forme `COMMANDE1 OPT1A OPT1B |
COMMANDE2 OPT2A OPT2B`.

Un exemple d'usage classique est de rediriger une commande dont la sortie est
très longue dans un pager (vu au chapitre 9). On peut par exemple essayer `sudo
dmesg | less` pour lire confortablement le résultat d'un `dmesg`.

## entrées et sorties

Les tubes fonctionnent grâce à deux concepts : les entrées et les sorties.

L'entrée permet d'alimenter un programme avec des données. Ainsi, dans
l'exemple précédent, la commande `less` se voit fournir des données (texte)
dans son entrée via le tube.

La sortie est l'endroit où le programme envoie sont résultat, généralement à
l'écran. Mais dans l'exemple du sous-chapitre précédent, le résultat de `dmesg`
est redirigé via le tube.

## Exercices

GameShell, niveaux 25 et 26.
