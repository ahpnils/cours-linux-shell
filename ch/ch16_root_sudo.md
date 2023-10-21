# Chapitre 16 : l'utilisateur root et sudo

Les systèmes GNU/Linux et Unix en général sont multi-utilisateurs : en plus de 
pouvoir gérer plusieurs comptes d'accès, il est possible de gérer les droits.
Mais cette gestion est surtout l'affaire d'un utilisateur en particulier :
root.

## root

L'utilisateur root est l'utilisateur administrateur du système. Il a **tous**
les droits, même ceux qui permettent de casser le système. Il peut modifier
tous les fichiers, changer tous les droits, créer, modifier et supprimer des
utilisateurs, etc... Associé à cet utilisateur se trouve un groupe, lui aussi
nommé root, qui ne devrait comporter qu'un seul membre ;-)

Sous les systèmes BSD, en lieu et place du groupe root, on trouve un groupe
wheel. Ce groupe existe aussi sous GNU/Linux, et sert pour les utilisateurs
ayant le droit d'effectuer des tâches administratives, en leur autorisant
l'accès au compte root ou à sudo.

Pour la plupart des distributions Linux, il existe par défaut deux moyens
d'accéder au compte root :

* directement depuis un terminal local non-graphique (login et mot de passe) ;
* via la commande `su -`.

Sous Ubuntu :

* le raccourci clavier Ctrl+Alt+F1 permet d'ouvrir une nouvelle session
  graphique ;
* le raccourci clavier Ctrl+Alt+F2 permet de revenir sur l'actuelle (première
  session graphique ;
* les raccourcis clavier Ctrl+Alt+F3 à F6 permettent d'accéder à des terminaux
  locaux non-graphiques.

À noter aussi, que sous Ubuntu, le compte root est par défaut désactivé : 
l'installation ne propose pas de lui paramétrer un mot de passe. Pour accéder à
la session de root sous Ubuntu, il faut utiliser `sudo`.

À noter une différence visible lors d'une session root : le prompt termine par
`#` au lieu de `$` pour un autre utilisateur. De plus, root possède toujours le
même numéro d'utilisateur (UID) : 0.

## sudo

`sudo` est un logiciel permettant de déléguer des tâches d'un utilisateur à un
autre. Il est particulièrement utilisé pour déléguer les tâches de root à un ou
plusieurs autres utilisateurs.

Sous Ubuntu, le premier compte configuré lors de l'installation se voit
attribuer des droits sudo étendus : il est donc possible d'effectuer toutes les
tâches d'administration en les préfixant par `sudo`. À noter que `sudo` demande
le mot de passe de l'utilisateur.

Pour vérifier la liste des droits délégués via `sudo`, il suffit de lancer la 
commande `sudo -l`.

Pour obtenir une session root complète, on lancera la commande `sudo -i`.

## Aparté sur l'historique des commandes

Dans bansh, il est possible de voir l'historique des commandes grâce à la
commande `history`. Chaque commande de l'historique est précédée par un numéro
qu'il est possible d'utiliser pour rappeler la commande. Pour rappeler la
commande numéro 5, il suffit alors de taper `!5`, et pour lancer une nouvelle
fois la commande qui vient d'être lancée, taper la commande `!!`.


## Exercices

Lancer la commande `dmesg`. Quel est le résultat ?
Lancer ensuite la commande `sudo dmesg`. Quel est le résultat ?
Lancer la commande `whoami`. Quel est le résultat ?
Lancer ensuite la commande `sudo !!`. Quel est le résultat ?
