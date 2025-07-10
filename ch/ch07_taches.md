# Chapitre 7 : mise d'un programme en arrière-plan et interruption

## Tâche de fond

Sur un ordinateur, de nombreux programmes sont en permanence en fonctionnement
: pour s'en convaincre, il suffit de lancer la commande `ps aux`. Mais tous ne
sont pas en attente d'une interaction de la part d'une utilisatrice ou d'un
utilisateur. Ils sont en arrière-plan.

Il est possible de lancer un programme dont on sait qu'on a pas besoin
d'interagir avec celui-ci en arrière-plan. Il suffit pour cela de le lancer
avec le caractère `&` à sa suite.

Mais il peut aussi arriver d'oublier de lancer le programme avec `&`. On peut
alors mettre en pause le programme via le raccourci clavier `Ctrl + Z`, puis
d'entrer la commande `bg` (pour *background*). On notera que le prompt ne
revient qu'une fois la commande bg entrée. Il est possible de repasser en
avant-plan avec la commande `fg` (pour *foreground*).

## Interruption

Il peut arriver de vouloir rapidement arrêter un programme qu'on vient de
lancer, pour de multiples raisons (il prend trop de ressources, option
manquante ou en trop, trop long à exécuter). Si ce programme est en avant-plan,
alors il est possible de l'interrompre avec le raccourci clavier `Ctrl + C`
(qui ne sert donc pas à effectuer une copie de texte).

## Exercices

GameShell, niveaux 18 et 19.
