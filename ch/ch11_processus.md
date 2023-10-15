# Chapitre 11 : gestion des processus

Nous avons vu au chapitre 7 qu'il était possible d'agir sur les programmes que
nous lançonns, mais il est possible d'agir sur tous les programmes du système.

## lister les processus en cours

Pour lister les programmes en cours d'exécution, il y a plusieurs programmes
pratiques, dont `ps`, `pstree` et `top`.

`ps` affiche à un instant donné la liste des processus en cours dans la
session. On voudra bien souvent aller plus loin, mais `ps` a la particularité
de prendre en charge plusieurs syntaxes : la syntaxe "historique" BSD et la
syntaxe "standard".

Les deux commandes suivantes sont alors identiques et affichent l'intégralité
des programmes en fonctionnement, en affichant le nom complet des commandes et
leurs options :

* `ps aux` ;
* `ps -ef`.

Il est généralement plus confortable de rediriger la sortie de ces commandes
dans un pager ;-)

`pstree` permet, de la même façon que tree, d'afficher les processus en cours
de fonctionnement dans une arborescence. On peut alors voir de façon assez
simple quel programme a lancé l'exécution d'un autre. Il est d'ailleurs
possible de limiter l'arborescence à un programme et ceux qu'il a lancés.

Par exemple, au moment d'écrire ce chapitre, j'utilise l'émulateur de terminal
Tilix, qui lui exécute un éditeur de texte, une page de manuel, une instance de
Gameshell et la commande `pstree`. Ayant trouvé le numéro de processus (PID) du
programme Tilix, je peux lancer :

```
$ pstree 3538
tilix─┬─bash───vim───{vim}
      ├─bash───gameshell.sh───bash─┬─_gsh_goal───pager───less
      │                            ├─gentille_fee─┬─3*[sortilege───sleep]
      │                            │              └─tail
      │                            └─lutin_espiegle─┬─3*[sortilege───sleep]
      │                                             └─tail
      ├─bash───pstree
      ├─bash───man───most
      └─11*[{tilix}]
```

L'oeil avisé remarquera les processus du niveau 29.

La commande `top` est différente, car elle reste à l'écran jusqu'à un appui sur
la touche Q. Elle affiche, en tri sur la consommation processeur, la liste des
programmes en cours de fonctionnement, mais donne aussi les ressources
processeurs et mémoire utilisées par ces programmes. C'est donc un outil
pratique de diagnostic si l'ordinateur fait face à des lenteurs.

`top` et `ps` sont des outils historiques, mais des outils récents ont fait
leur apparition, comme [htop](http://hisham.hm/htop/),
[btop](https://github.com/aristocratos/btop), ou
[glances](https://nicolargo.github.io/glances/).

## agir sur les processus : kill

Sous Unix, il est possible d'interagir avec les programmes via des signaux. Ces
signaux sont numérotés et correspondent à un type d'action. La commande `kill`
permet d'envoyer un signal à un processus, via l'option `-s`. Si aucun signal
n'est précisé, le signal TERM est envoyé pour terminer proprement le programme.


Quelques signaux :

* 2 (SIGINT) : interrompt le processus, de la même manière qu'un Ctrl+C ;
* 9 (SIGKILL) : tue le programme ;
* 15 (SIGTERM) : termine le programme (proprement).

Il est assez courant de `kill -s 9` ou de `kill -9` (vieille syntaxe) un
programme récalcitrant.

`kill` a besoin non pas du nom du programme, mais de son numéro de processus,
appelé PID. Ce PID est donnée par `top` et `ps`.

## modifier la priorité des processus avec nice

Dans le cas d'un programme dont on sait qu'il va prendre presque toutes les
ressources processeur, il est possible de le lancer dans une commande qui
limitera l'accès : `nice`. 

## Exercices

GameShell, niveaux 27 à 29.
