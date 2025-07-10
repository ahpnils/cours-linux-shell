# Annexe 2 : l'aide et la documentation

Les systèmes Unix, en particulier libres, disposent de nombreuses
documentations. Voici un point de départ.

## Les pages de manuel

Toutes les commandes "de base" ou presque disposent d'une page de manuel, qui
regroupe l'usage de la commande ainsi que la documentation des différentes
options. Pour accéder à cette page de manuel, on utilise la commande `man`. Par
exemple, pour rechercher les options de `ls` et savoir comment afficher les
fichiers cachés, on peut taper `man ls`. On lira alors dans la partie
"DESCRIPTION" que l'option `-a` affiche les fichiers commençant par « . », qui
sont les fichiers cachés.

Les pages de manuel sont organisées par sections, dont la liste est données par
la commande `man man`. À noter qu'il est possible qu'un même nom soit
disponible dans plusieurs sections : par exemple, `man crontab` documentera la
commande `crontab` mais `man 5 crontab` décrira comment remplir un fichier de
confiration de `crontab` (la section 5 sert aux fichiers de configuration).

À noter que toutes les commandes ne disposent pas d'une page de manuel.
Certains projets fournissent des logiciels en ligne de commande, accompagnés de
documentation, sur leur propre site web, mais pas sous forme de page de manuel.

Il est possible que sur certains OS, les pages de manuel ne soient pas
installées. Heureusement, il existe des pages web qui rassemblent les pages de
manuels des commandes "de base" et des logiiels les plus connus :

* https://linux.die.net/man/ ;
* https://www.man7.org/linux/man-pages/index.html ;
* https://manpages.org/ .

Pour en savoir plus sur les pages de manuel : [l'excellente vidéo de Yves
Rougy](https://www.youtube.com/watch?v=W5dsJzViQsA).

## Autres aides et documentation

Une alternative à la commande `man` peut être de rechercher de la documentation
sur le site du projet concerné par la commande, ou sur l'un des sites web
dédiés à la documentationn de la distribution Linux utilisée. Voici quelques
liens selon des distributions populaires.

Ubuntu :

* https://docs.ubuntu.com/ ;
* https://help.ubuntu.com/ ;
* https://ubuntu.com/tutorials ;
* https://doc.ubuntu-fr.org/ (site francophone maintenu par une communauté,
  non-affilié à la société Canonical, éditeur de la distribution Ubuntu).

Debian :

* https://wiki.debian.org/fr/FrontPage?action=show&redirect=PageD%27Accueil ;
* https://www.debian.org/doc/ ;
* https://www.debian.org/doc/user-manuals.fr.html .

Ubuntu étant basée sur Debian, bon nombre de commandes et de propriétés des
deux OS sont communes.

Fedora : 

* https://docs.fedoraproject.org/en-US/docs/ ;
* https://doc.fedora-fr.org/wiki/Accueil (site francophone maintenu par une
  communauté, non affilié ni au projet Fedora ni à la société Red Hat).

RHEL (Red Hat Enterprise Linux) :

* https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/ ;
* https://developers.redhat.com/ .

À noter que, dans une certaine limite, bon nombre de documentations pour RHEL
sont valables pour les "clones" (CentOS Stream, Oracle Linux, Almalinux, Rocky
Linux, etc...). C'est aussi valable, dans une moindre mesure, pour Fedora
(projet sous mécénat de Red Hat, Fedora servant de base à CentOS Stream,
laquelle servant ensuite de base à RHEL).

Projets divers de documentation et d'aide :

* https://lea-linux.org/ ;
* https://www.linuxtricks.fr/wiki/wiki.php ;
* https://www.server-world.info/en/ .
