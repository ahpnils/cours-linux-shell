# Chapitre 2 : les commandes de base

## Le système de fichiers, s'y déplacer

### L'arborescence

Sous Unix, et Linux en particulier, tout est fichier. Toute interaction avec le
système devient donc une interaction avec des fichiers. Ici par contre, pas de
lettre de lecteur. Le système de fichiers fonctionne en arborescence, avec une
racine dont l'emplacement est `/`.

Il y a une convention (FHS, Filesystem Hierarchy Standard) qui indique quels
types de contenus doivent se trouver dans quels répertoires. Quelques
indispensables à retenir :

- `/etc/` contient les fichiers de configuration système (mais aussi pour des
  programmes) ;
- `/home/` contient les répertoires personnels des utilisateurs (un répertoire
  par utilisateur, ainsi l'utilisateur `nils` a pour répertoire personnel
  `/home/nils/`) ;
- exception au chemin précédent, l'utilisateur administrateur, nommé `root`, a
  pour répertoire personnel `/root/` ;
- `/bin/`, `/usr/bin/` ou encore `/usr/local/bin` contiennent des programmes
  (des fichiers binaire exécutables), tandis que `/sbin/`, `/usr/sbin/` ou
  `/usr/local/sbin/` contiennent des programmes utilisés pour l'administration
  du système, nécessitant des droits étendus ;
- `/tmp/` contient des fichiers temporaires ;
- et `/var/log/` sert à stocker des fichiers journaux, pour le système et les
  programmes.

Il existe aussi des chemins spéciaux :
- `.` désigne le répertoire courant ;
- `..` désigne le répertoire parent, c'est-à-dire le répertoire juste au-dessus
  du répertoire courant dans l'arborescence ;
- `~` désigne le répertoire personnel de l'utilisateur.

Ces chemins peuvent être utilisés comme arguments ou options pour des
commandes.



### pwd

Lors du démarrage d'une session (via l'ouverture d'un émulateur de terminal par
exemple), sauf problème, le répertoire courant est le répertoire personnel de
l'utilisateur. Ce répertoire peut, au lieu de son chemin, être désigné par le
symbole `~` dans le prompt. Dans le cas où le prompt ne l'indique pas, on peut
utiliser la commande `pwd` (_Print Working Directory_) pour l'afficher.

### cd

La commande `cd` (_Change Directory_) permet de changer de répertoire courant.
Elle dispose de quelques possibilités assez intéressantes :

- `cd` sans argument nous ramène dans notre répertoire personnel, peu importe
  le répertoire courant ;
- `cd -` nous ramène dans le répertoire précédent, par rapport à l'historique
  de navigation, à ne pas confondre avec le répertoire parent.

### ls

La commande `ls` (_List Short_) affiche le contenu du répertoire courant. Là
aussi quelques options intéressantes :

- `ls -l` ;
- `ls -a` et `ls -A` ;
- `ls <chemin>`.

### Chemins absolus et relatifs

Un chemin absolu est un chemin écrit en entier, et qui commence donc par la
racine. Par exemple, `/srv/www/anotherhomepage.org/public/` est un chemin absolu.

Un chemin est dit relatif lorsqu'il ne commence pas par la racine. Il est donc
relatif à l'emplacement de l'utilisateur dans l'arborescence. 

Prenons par exemple un répertoire `/srv/www/anotherhomepage.org` qui contient
les répertoires suivants :

```
.
|-- log
|-- public
|   `-- .well-known
|-- session
`-- tmp
```

Depuis ce répertoire, il est possible de se déplacer dans le répertoire `log`
en tapant tout simplement `cd log`. Et une fois dans ce répertoire, il est
possible en une seule commande d'aller dans le répertoire `session` via `cd
../session`.

## Action sur les fichiers et répertoires

Comme sur un environnement graphique, il est possible d'effectuer des actions
sur les fichiers et répertoires, comme :

- créer un répertoire, via la commande `mkdir` ;
- supprimer, avec `rm` ;
- déplacer : `mv` (qui peut aussi servir à renommer) ;
- copier, avec `cp`;

### mkdir

`mkdir` ("MaKe DIRectory") crée un répertoire dans l'arborescence, ou plusieurs
grâce à l'option `-p`.

### rm

`rm` ("ReMove") supprime des fichiers. Par défaut, aucune demande de confirmation
n'est demandée. Quelques options intéressantes :

- `-v` affiche les noms des fichiers effacés ;
- `-i` demande une confirmation ;
- `-r` est récursif (on peut alors supprimer toute une arborescence avec une
  seule commande) ;
- `-f` ignore les fichiers qui n'existent pas, ne demande jamais confirmation.

### cp

`cp` ("CoPy") effectue une copie. On y trouve des options similaires à `rm` :

- `-v` affiche les noms des fichiers copiés ;
- `-i` demande une confirmation en cas de fichier cible déjà existant ;
- `-r` est récursif (on peut alors copier toute une arborescence avec une
  seule commande) ;
- `-f` ignore les fichiers existant à la cible, ne demande jamais confirmation.

À noter une option `-p` qui conserve les attributs des fichiers.

### mv

`mv` ("MoVe") déplace des fichiers. On peut aussi s'en servir pour renommer un fichier.
Il a lui aussi des options assez similaires à `rm` et `cp` :

- `-v` affiche les noms des fichiers déplacés ;
- `-i` demande une confirmation en cas de fichier cible déjà existant ;
- `-r` est récursif (on peut alors bouger toute une arborescence avec une
  seule commande) ;
- `-f` ignore les fichiers existant à la cible, ne demande jamais confirmation.

### Exercices

Passer les niveaux 1 à 12 de GameShell.
