# Chapitre 12 : redirections d'entrées et de sorties

Nous avons vu dans le chapitre 10 qu'il était possible de rediriger le résultat
(la sortie) d'un programme dans un autre (son entrée). Mais il est possible
d'aller plus loin.

## Rediriger l'entrée standard 

L'entrée découverte lors du chapitre 10 se nomme en réalité l'entrée standard.
Par défaut, l'entrée standard désigne le clavier, qui permet de taper des
commandes (et leurs options) ainsi que des paramètres (dans le cas de
programmes interactifs). Mais pour aller plus vite il est possible de changer
ponctuellement cette entrée, en utilisant un fichier. La syntaxe est
globalement la suivante : `COMMANDE < FICHIER`.

On retrouve aussi souvent comme dénomination de l'entrée standard "stdin" (pour
standard input).

## Rediriger la sortie standard

Tout comme l'entrée, la sortie se nomme sortie standard, l'endroit où le 
programme envoie sont résultat, généralement à l'écran. Il est aussi possible
de rediriger cette sortie dans un fichier, plutôt que d'écrire (ou de
copier-coller) le résultat soi-même. La syntaxe est la suivante : `COMMANDE >
FICHIER`.

Un usage régulier de cette redirection est de "faire taire" un programme en
redirigeant sa sortie dans un fichier spécial,
[`/dev/null`](https://fr.wikipedia.org/wiki/P%C3%A9riph%C3%A9rique_nul). Ce fichier a pour
particularité de supprimer tout ce qui est écrit dedans.

On retrouve aussi souvent comme dénomination de la sortie standard "stdout" (pour
standard output).

## Rediriger la sortie d'erreur

En plus de la sortie standard, on retrouve la sortie d'erreur. En effet, les
programmes peuvent utiliser une deuxième sortie, dédiée aux messages d'erreur.
Cette sortie est elle aussi par défaut sur l'écran. Pour la rediriger vers un
fichier, on peut alors utiliser la syntaxe `COMMANDE 2> FICHIER`.

On peut utiliser plusieurs redirections en une fois, et rediriger dans
plusieurs fichiers, ou même un seul, commun. Une utilisation classique pour
vraiment "faire taire" un programme est de rediriger à la fois la sortie
standard et la sortie d'erreur dans `/dev/null`, comme ceci : `COMMANDE >
/dev/null 2>&1`. La partie `&1` permet de dire de rediriger la sortie d'erreur
dans la sortie standard.

On retrouve aussi souvent comme dénomination de la sortie d'erreur "stderr" (pour
standard error).

## grep

## Exercices

GameShell, niveaux 30 à 34.
