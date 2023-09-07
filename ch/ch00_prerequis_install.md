# Chapitre 0 : prérequis et installation de GameShell

## Prérequis

Ce cours est basé sur l'interpréteur de commandes Bash ; dans l'absolu, ce
logiciel est disponible sous de nombreux systèmes d'exploitation, mais ce cours
étant initialement donné aux M2 TNAH de l'Ecole Nationale des Chartes, seul le système
d'exploitation Ubuntu, au minimum dans sa version 22.04 LTS est pris en charge.

Les étudiantes et étudiants sont fortement encouragés à utiliser le matériel
informatique mis à leur disposition par l'Ecole durant les cours. Ce matériel
répond aux critères de configuration requis pour suivre le cours.

Afin de pouvoir travailler les cours en dehors des heures de classe, il est
recommandé de disposer aussi d'un système Ubuntu, soit dans une machine
virtuelle, soit sur une machine dédiée à cet usage.

Il est possible de voir les prérequis matériels pour l'installation d'Ubuntu
[sur la page de téléchargement](https://ubuntu.com/download/desktop). Le site
d'Ubuntu propose aussi un [guide
d'installation](https://help.ubuntu.com/20.04/installation-guide/index.html).
Bien que basé sur une ancienne version, celui-ci devrait être toujours valide.

Si jamais Ubuntu s'avère trop lourd, ou que les prérequis matériels ne sont pas
atteints, une alternative possible est
[Xubuntu](https://xubuntu.org/download/), toujours au minimum la version 22.04
LTS. Les prérequis matériels peuvent être examinés [sur cette
page](https://xubuntu.org/requirements/), et la documentation d'installation
d'Ubuntu devrait être valide pour Xubuntu.

Pour les machines Apple équipées de processeurs Apple Silicon (processeurs de
gamme M1 et M2), le plus simple est d'utiliser le logiciel de virtualisation
[UTM](https://mac.getutm.app/), et d'effectuer une installation soi-même. Les
images prêtes à l'emploi (dans la rubrique "Gallery" du site) sont dans
l'ensemble trop anciennes).

## Installation de GameShell

GameShell est un jeu en mode texte permettant d'apprendre les rudiments de la
ligne de commande. Celui-ci propose des exercices sous forme de niveaux, dans
un univers de type médiéval-fantastique.

Une fois le système Ubuntu ou Xubuntu installé, démarrer l'application
"terminal", et lancer les commandes suivantes, qui installeront les prérequis
pour utiliser GameShell (une commande par ligne) :

```
sudo apt update
sudo apt install gettext man-db procps psmisc nano tree bsdmainutils x11-apps wget
```

Ensuite, télécharger GameShell :

```
wget https://github.com/phyver/GameShell/releases/download/latest/gameshell.sh
```

Et enfin, pour l'exécuter :

```
bash gameshell.sh
```

Appuyer sur la touche "Entrée" une première fois, puis une deuxième fois à
l'issue de l'introduction (dont la lecture est recommandée). Une fois au
prompt du niveau 1, taper la commande `exit` puis appuyer sur la touche
"Entrée" pour quitter le jeu.

