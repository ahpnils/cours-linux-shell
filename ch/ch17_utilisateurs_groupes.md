# Chapitre 16 : l'utilisateur root et sudo

Les systèmes GNU/Linux et Unix en général sont multi-utilisateurs : il est donc
possible d'avoir plusieurs utilisateurs partageant une même machine, et des
fichiers.

## Etape 4 : gestion des utilisateurs

Un utilisateur a été créé lors de l'installation, mais il est possible de créer
d'autres utilisateurs une fois le système installé.

Lancer la commande suivante, en tant que root :
```
useradd -m -U -u 2001 -s /bin/bash student1
```

Celle-ci crée un utilisateur, dont les propriétés sont les suivantes :

* son login est `student1` ;
* son shell (`-s`) est `/bin/bash` ;
* son UID (`-u`) est `2001` ;
* son groupe principal est aussi `student1`, et son GID `2001` (`-U`) ;
* son répertoire "home" est créé (`-m`).

Créer maintenant deux utilisateurs :

* `student2` et `student3` ;
* leur shell sera `/bin/bash` ;
* leurs UID sont respectivement `2002` et `2003` ;
* les GID et groupes principaux seront identiques aux UID et logins ;
* `student2` fera partie du groupe `staff` (option `-G`) ;
* `student3` fera partie du groupe `users` ;
* les répertoires "home" sont créés.

Vérifier que tout est bien créé dans les contenus des fichiers `/etc/passwd` et
`/etc/group`. Vérifier la présence des répertoires utilisateurs dans `/home`.

Toujours en tant que root, ajouter un mot de passe aux trois comptes créés dans
cette étape. Par exemple, la commande `passwd student1` permet de modifier le
mot de passe du compte `student1`. Se déconnecter de la session root et
vérifier que le mot de passe est bien fonctionnel sur chaque compte.

## Etape 5 : gestion des groupes

En tant que root, créer un répertoire `/home/groups`. S'assurer que tous les
utilisateurs du système peuvent entrer dans ce répertoire avec la commande
`chmod 0755 /home/groups`. Créer ensuite dans ce répertoire trois fichiers
textes, et modifier les groupes propriétaires pour obtenir le résultat suivant
:

- `/home/groups/student1.txt` ayant comme groupe propriétaire "student1" ;
- `/home/groups/staff.txt` ayant comme groupe propriétaire "staff" ;
- `/home/groups/users.txt` ayant comme groupe propriétaire "users".

Pour modifier les groupes propriétaires, utiliser la commande `chgrp` ou `chown`.

Modifier ensuite les droits des trois fichiers de façon à ce qu'ils soient
accessibles en lecture et écriture pour le propriétaire et le groupe, mais
seulement en lecture pour les autres utilisateurs.

Ensuite, se connecter successivement en tant que student1, student2, student3,
puis student (dans cet ordre), et tenter d'ajouter du texte dans chacun des
trois fichiers créés.

Question : quels utilisateurs peuvent écrire dans quels fichiers ? Est-ce en
accord avec les droits configurés ?

Il est possible d'ajouter ou de retirer un utilisateur existant à un ou
plusieurs groupes sur un système, via la commande `usermod` : l'option `-G`
définit une nouvelle liste de groupes (secondaires), et `-a` permet que cette
liste soit un ajout (l'utilisateur n'est donc pas retiré des groupes non
définis). Ajouter les utilisateurs student1, student2 et student3 aux groupes
`staff` et `users`, puis tenter d'écrire à nouveau dans les trois fichiers
depuis ces utilisateurs.

Créer un groupe `students` via la commande `groupadd`, dont le GID sera 1337.
Ajouter ensuite les utilisateurs student1, student2 et student3 à ce
groupe. Créer un répertoire `/home/groups/students` et lui donner les droits
de lecture, écriture et exécution pour le propriétaire, et le groupe, mais
aucun droit pour les autres utilisateurs. Vérifier ensuite que cela fonctionne
: depuis chaque session utilisateur, créer dans ce répertoire un fichier texte
au nom de celui-ci, et le rendre accessible en lecture et en écriture pour
lui-même, en lecture pour le groupe, et aucun droit pour les autres.

## Etape 6 : suppression des utilisateurs et groupes

Utiliser les commandes `userdel` et `groupdel` pour faire le ménage (en tant
que root).
