# Chapitre 1 : présentation de l'interpréteur en ligne de commande : le shell Bash

## Présentation du terminal

Bien avant les ordinateurs personnels et les interfaces graphqiques, les
premiers ordinateurs sont tellement grands qu'ils prennent des salles entières.
Les moyens d'interactions (clavier, écran) sont donc déportés, parfois sur de
longues distances. On appelle alors ces points d'accès [des
terminaux](https://fr.wikipedia.org/wiki/Terminal_(informatique).

Aujourd'hui, un émulateur de terminal ou un terminal désigne plutôt un
programme donnant accès à une interface en ligne de commande, généralement un
shell Unix.

Un aperçu des terminaux et des ordinateurs auxquels ils accédaient est
disponible dans [cette vidéo de 8-bit
guy](https://www.youtube.com/watch?v=cRM7mUqLiws).

## L'interpréteur de commandes Bash

Depuis la création d'Unix, il y a eu plusieurs interpréteurs de commandes : le
premier se nommait `sh`, mais le fichier `/bin/sh` disponible sur de nombreuses
distributions grand public n'a plus rien avoir avec. Il s'agit généralement
d'une redirection vers Bash.

[Bash](https://www.gnu.org/software/bash/) est l'interpréteur de commandes issu 
du [projet GNU](https://fr.wikipedia.org/wiki/GNU), et est devenu le shell le 
plus populaire des systèmes Unix, libres comme propriétaires. Il est aussi celui 
par défaut de bon nombre de ces systèmes, dont Ubuntu. Il n'est donc pas
nécessaire de chercher à l'installer, et celui-ci est démarré lors du lancement
de l'application "Terminal". Bash est aussi l'interpréteur utilisé pour
l'interface texte lorsque pour une raison ou une autre, l'interface graphique
ne démarre pas.

## Anatomie d'une commande

Tout d'abord, qu'est-ce qu'une commande ? Il peut s'agit de deux choses :

* soit d'une instruction interne au shell, on parle alors de "built-in" ;
* soit d'un autre programme, externe au shell.

Dans ce deuxième cas, le programme peut être exécuté en spécifiant son chemin 
(relatif ou absolu, nous y viendrons dans un prochain chapitre), ou pas, si
celui-ci est présent dans un ensemble de répertoires connus et pris en compte
par le shell (on appelle ça le "path", du nom d'une variable d'environnement
nommée $PATH, nous y viendrons aussi plus tard).

La commande `type` permet de voir si une commande est built-in ou externe.

Exercice : vérifier, en tapant `type nomdelacommande`, si les commandes `pwd`,
`cd` et `ls` sont des built-ins ou des commandes externes.

Nous venons de taper nos premières commandes, et avec celles-ci nos premiers
arguments. Une commande peut en effet être suffixée par des options ou des
arguments. Voici un exemple de commande :

```
wget --no-verbose -O ~/Pictures/compile.png https://medias.anotherhomepage.org/pix/compile_tools.png
```

* `wget` est le programme appelé ;
* `--no-verbose` est une option longue ;
* `-O` est une option courte ;
* `~/Pictures/compile.png` est un premier argument ;
* `https://medias.anotherhomepage.org/pix/compile_tools.png` est un deuxième
  argument.

On notera que les options et les arguments sont séparés par des espaces, mais
les versions courtes peuvent être collées ensembles, comme par exemple dans le
cas de la commande `rsync -av
rsync://rsync.kernel.org/pub/linux/kernel/v1.0/linux-1.0.tar.gz`.


## Extras :

* Pour connaître la liste des shells configurés sur le système, taper la
  commande `cat /etc/shells` ;
* pour savoir quel est le shell en cours d'exécution, taper la commande `echo
  $SHELL` ;
* Découvrir Linux, épisode 1 : [À quoi sert le système
d'exploitation](https://www.youtube.com/watch?v=EYRWohJeCkk) ;
* Découvrir Linux, épisode 2 : [Le
  terminal](https://www.youtube.com/watch?v=t7Ci2hwUpIM&list=WL&index=26).
