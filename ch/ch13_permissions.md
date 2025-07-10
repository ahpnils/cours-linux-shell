# Chapitre 13 : les permissions

Tous les systèmes d'exploitation modernes partent du principe qu'un fichier ou
un répertoire possède des attributs de type permissions. Il est possible de
voir et de modifier ces droits, sur des fichiers ou des répertoires.

## voir les permissions

Un moyen très simple de voir les permissions sur des répertoires ou des
fichiers est d'utiliser l'option `-l` de `ls` : en plus d'afficher
l'utilisateur, le groupe propriétaire et la taille de ceux-ci, on peut y lire
des caractères particuliers sur la gauche. Voici un exemple (la même commande 
sur un autre système peut avoir un résultat différent) :

```
$ ls -l /var/log | head -n 6
total 14832
drwxrwxr-x. 2 root    akmods             4096  1 oct.  15:38 akmods
drwxr-xr-x. 2 root    root               4096 12 déc.   2020 anaconda
drwx------. 2 root    root               4096 16 oct.  18:08 audit
-rw-------. 1 root    root               4367 16 oct.  17:57 boot.log
-rw-------. 1 root    root              41364  5 oct.  20:10 boot.log-20231005
```

On remarquera que certains fichiers commencent par la lettre `d` : il s'agit de
répertoires. On notera que les caractères `r`, `w`, `x` et `-` reviennent
régulièrement :

* `r` désigne le droit de lecture ;
* `w` désigne le droit d'écriture ;
* `x` désigne le droit d'exécution (ou de traversée dans le cas d'un
  répertoire) ;
* `-` désigne l'absence du droit.

Ces droits sont positionnés pour trois catégories d'utilisateurs, de gauche à
droite :

* en premier, l'utilisateur propriétaire du fichier ;
* ensuite, le groupe propriétaire du fichier ;
* enfin, les autres utilisateurs sur le système.

Avec ces informations, il est possible de décoder les droits aperçus plus haut
:

* l'utilisateur root et les membres du groupe akmods ont le droit de lire,
  d'écrire et de traverser le répertoire `akmods`, mais les autres utilisateurs
  ne peuvent que lire et traverser ce répertoire ;
* seul root peut consulter, modifier et traverser le répertoire `audit` ;
* seul root peut lire et modifier `boot.log`, mais il ne peut pas l'exécuter
  (fort heureusement, au vu du nom, ce n'est pas un programme).

## changer les permissions : chmod

Il est possible de changer les permissions sur un fichier ou un répertoire
grâce à la commande `chmod`. Il y a plusieurs syntaxes pour cela.

La première, plus facile à comprendre mais plus longue à taper, reprend en
partie les codes vus avec `ls`. Ainsi, en supposant que nous sommes
l'utilisateur root, pour ajouter le droit de lecture pour le groupe et les
autres utilisateurs au fichier `/var/log/boot.log` rencontré plus haut, on peut
lancer la commande suivante : `chmod g=r,o=r /var/log/boot.log`.

La syntaxe va donc être `chmod  <options> <permissions> <fichier>`. Les
permissions sont positionnées pour l'utilisateur propriétaire du fichier (user) 
avec la lettre u, pour le groupe propriétaire (group) avec la lettre g, et pour 
les autres utilisateurs (ceux n'étant ni le propriétaire ni membres du groupe)
avec la lettre o (others). On peut alors ensuite spécifier les droits,
comme r (read), w (write) et x (execution).

Une deuxième syntaxe, plus courte, et de prime abord moins lisible, utilise des
codes chiffŕes :

* 0 pour l'absence de droits ;
* 1 pour l'accès en exécution ;
* 2 pour l'accès en écriture ;
* 4 pour l'accès en lecture.

Ces chiffres sont additionnés pour obtenir les droits. Les combinaisons les
plus utilisées sont :

* 0 pour l'absence de droits ;
* 4 pour l'accès en lecture ;
* 5 pour l'accès en lecture et exécution (4 + 1) ;
* 6 pour l'accès en lecture et écriture (4 + 2) ;
* 7 pour l'accès en lecture, écriture et exécution (4 + 2 + 1).

Pour chaque catégorie d'utilisateur, on peut alors spécifier le droit. À noter
que contrairement à la syntaxe précédente, il faut obligatoirement spécifier
les droits pour chaque catégorie. L'équivalent de `chmod g=r,o=r
/var/log/boot.log` devient donc `chmod 644 /var/log/boot.log` (car root avait
déjà les droits de lecture et d'écriture, donc le 6 n'ajoute finalement rien).

Pour plus de renseignements sur ces codes, il est possible de consulter la page
de manuel `man 2 chmod`.

`chmod` possède aussi des options, parmi lesquelles :

* `-v` augmente la verbosité ;
* `-R` active la récursion.

Il convient de faire attention avec la récursion, comme en témoigne [cette
vidéo](https://youtu.be/UT6ZkAa9m9A?si=KbQr3BcOYtHdEo6c&t=6573) (réalisée sur
un système jetable, et à ne pas reproduire chez soi).

## Exercices

GameShell, niveaux 37 à 39.

## Exercice complémentaire

Jusqu'à maintenant, pour lancer le jeu Gameshell, la commande `bash
gameshell.sh` était utilisée. Rendre le fichier `gameshell.sh` exécutable puis
vérifier en utilisant la commande `./gameshell.sh` pour le lancer.
