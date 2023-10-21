## gestion des paquets logiciels

Ubuntu, comme de nombreuses distributions Linux, permet d'installer des
logiciels via des paquets, disponibles dans des dépôts. On peut assimiler
l'installation de paquets logiciels à l'installation d'applications depuis le
"store" de son smartphone. De la même façon, il est possible d'installer des
paquets directement depuis des fichiers téléchargés (comme on peut directement
installer des fichiers `.apk` sous Android, mais les bonnes pratiques
découragent cet usage).

Sous Ubuntu, `dpkg` et `apt` permettent de gérer les paquets logiciels, au
format ".deb". Le premier est un outil basique, alors que le second est bien
plus avancé et permet de gérer les dépendances (un logiciel ayant besoin d'un
autre ou d'une bibliothèque pour fonctionner).

La commande `dpkg --list` permet d'afficher la liste des paquets installés sur
le système. Dans cette liste, les lignes comportant les logiciels installés
commencent par `ii`.

Question : combien de logiciels sont installés ?

Question : les paquets tmux, rsync et openssh-server sont-il installés ? Si
oui, en quelle version ?

Le logiciel `apt` permet les actions suivantes :

- `apt install <package>` installe le paquet "package" ;
- `apt search <package>` recherche le paquet "package" dans les dépôts ;
- `apt purge <package>` désinstalle le paquet "package" ;
- `apt update` met à jour le cache local contenant la liste des paquets
  disponibles ;
- `apt upgrade` met à jour les paquets installés.

À l'aide de ces commandes, effectuer les actions suivantes dans l'ordre :
- mettre à jour le cache local des paquets disponibles ;
- installer les logiciels suivants : tmux, sl, et tilix ;
- après avoir essayé la commande `sl`, désinstaller le paquet "sl".

Attention, certaines de ces commandes nécessitent les droits root !

Question : est-ce que des mises à jour de paquets sont disponibles ?

## gestion des dépôts de logiciels

Passons à la gestion des dépôts logiciels. Ceux-ci sont configurés à plusieurs
endroits : dans le fichier `/etc/apt/sources.list`, ou dans un fichier dont
l'extension se termine par `.list` et se trouvant dans le répertoire
`/etc/apt/sources.list.d`.

Question : quel est le contenu de `/etc/apt/sources.list` et de
`/etc/apt/sources.list.d` ?

Nous allons ajouter un dépôt tiers, fournissant des logiciels supplémentaires.
Il s'agit d'un dépôt non-affilié à Ubuntu, mais créé par une personne de
confiance, développeur Debian et contributeur à PHP. Pour faciliter notre
tâche, nous allons utiliser un PPA (Personal Package Archive). Ce dépôt tiers
nous donnera accès à des versions supplémentaires de PHP.

Question : quelle est la version de PHP disponible sous Ubuntu ?

Lancer les commandes suivantes (et confirmer lorsque c'est nécessaire) :

```
sudo add-apt-repository ppa:ondrej/php
sudo apt update
```

Questions : 

* quelles sont maintenant les versions de PHP disponible sous Ubuntu ?
* quel est maintenant le contenu de `/etc/apt/sources.list` et de `/etc/apt/sources.list.d` ? 

## Autres moyens

Il est possible d'installer des logiciels par d'autres moyens, soit en
compilant soi-même, soit en utilisant d'autres technologies, comme
[Snap](https://doc.ubuntu-fr.org/snap),
[Flatpak](https://doc.ubuntu-fr.org/flatpak) ou
[Appimage](https://doc.ubuntu-fr.org/appimage). La solution privilégiée à ce
jour par Canonical est Snap.
