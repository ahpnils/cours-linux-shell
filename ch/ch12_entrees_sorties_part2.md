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

## Redirection à la fin du fichier

Nous avons vu qu'il est possible de rediriger une sortie dans un fichier mais
que se passe-t'il si le fichier possède déjà un contenu ? Expérimentons à
l'aide d'un exemple concrêt :

```
echo "foo" > ~/foo.txt
echo "bar" > ~/foo.txt
cat ~/foo.txt
```

À l'issue de ces commandes, `~/foo.txt` contient uniquement "bar". Pour pouvoir ajouter
du texte à la suite du contenu existant, la syntaxe est légèrement différente,
voici un nouvel exemple :

```
echo "foo" > ~/bar.txt
echo "bar" >> ~/bar.txt
cat ~/bar.txt
```

À l'issue de ces commandes, le contenu de `~/bar.txt` est :

```
foo
bar
```

Note : il est possible d'utiliser `>>` dès le premier ajout.

## grep

Nous avons vu les possibilités de lire un fichier, page par page, ou d'en
afficher qu'une partie, haute ou basse. Mais il est aussi possible de filtrer
le contenu d'un fichier, grâce à `grep`.

Par exemple, `grep http /etc/services` va rechercher dans le fichier
`/etc/services` toutes lignes contenant la chaîne `http`. `grep` est très
puissant et permet par exemple :

* de faire une recherche insensible à la casse, avec l'option `-i` ;
* d'inverser le filtre (donc d'afficher les lignes ne contenant pas la chaîne
  de caractères demandée), avec `-v` ;
* de rechercher un mot entier (séparé par des espaces), grâce à `-w` ;
* d'utiliser des [expressions
  rationnelles](https://fr.wikipedia.org/wiki/Expression_r%C3%A9guli%C3%A8re),
  via l'option `-E`.

Un des nombreux usage de grep, en plus de rechercher du texte dans des
fichiers, est de filtrer la sortie d'une commande, par exemple : `ps aux | grep
-i systemd` recherche dans la liste des processus en cours de fonctionnement
les lignes comportant la chaîne "systemd".

## Exercices

GameShell, niveaux 30 à 34.
