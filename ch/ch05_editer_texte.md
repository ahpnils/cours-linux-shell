# Chapitre 5 : éditer du texte

## nano

[Nano](https://fr.wikipedia.org/wiki/GNU_nano) est un logiciel d'édition de texte
 en ligne de commande. Il est très apprécié des débutants, du fait de sa
simplicité d'utilisation et de l'aide affichée en permanence en bas de l'écran.

Deux raccourcis pratiques provenant de cette aide :

- Ctrl+O pour sauvegarder ;
- Ctrl+X pour quitter : nano demande alors si on souhaite sauvegarder.

### Exercice

GameShell, niveaux 15 et 16.

## vi et Vim

[Vi](https://fr.wikipedia.org/wiki/Vi) est un autre éditeur de texte, qui nous
provient d'UNIX et datant de 1976. En réalité sur un système d'exploitation
moderne, on trouvera plutôt Vim, (pour Vi IMproved). Créé par Bram Moolenaar en
1991, celui-ci peut dérouter par son système de fonctionnement dit "modal".

Il y a trois modes :

- le mode normal, ou commande, par défaut, qui ne permet pas d'éditer du texte ;
- le mode insertion, qui permet d'éditer du texte ;
- le mode ligne de commande.

Vi datant d'une époque où les claviers n'avaient pas de touches fléchées, les
touches h,j,k,l permettent de se déplacer dans le texte, respectivement à
gauche, bas, haut, droite. Ces commandes ne sont accessibles que dans le mode
commande. Quelques autres commandes pour "survivre avec vi/Vim" :

- deux touches permettent d'entrer en mode insertion : `a` (append) et `i`
  (insert) ;
- une fois l'édition terminée, il est possible de retourner en mode commande
  via la touche "Echap" ;
- pour quitter, la commande est ":q", mais ne fait pas de sauvergarde ;
- pour sauver le fichier, la commande est ":w", et peut être combinée à celle
  de quitter, ce qui donne ":wq" ;
- il existe deux versions raccourcies pour sauver et quitter un fichier sous
  Vim (toujours en mode commande): "ZZ" et ":x" ;
- ajouter "!" à la fin de la commande pour forcer son exécution ; ainsi on
  pourra trouver dans de nombreux tutoriaux sur "comment quitter Vim" la
  réponse "Echap, puis :wq!".

### Exercice

Installer Vim à l'aide de la commande `sudo apt -y install vim`, puis lancer la
commande `vimtutor`. Le tutoriel ainsi lancé comporte plusieurs leçons.
Effectuer les leçons  1.1 à 1.6 et lire le résumé qui suit.

Note pour les plus courageuses et courageux : `vimtutor` va jusqu'à la leçon
7.3.

## Autres logiciels

Il existe d'autres éditeurs de texte disponibles en mode texte :

- [GNU Emacs](https://fr.wikipedia.org/wiki/GNU_Emacs), du projet GNU, bien
  souvent comparé à Vi/Vim lors de débats stériles et sans fin sur la
  supériorité de l'un ou l'autre des logiciels ;
- [Pico](https://fr.wikipedia.org/wiki/Pico_(logiciel)), similaire à nano ;
- [JOE](https://fr.wikipedia.org/wiki/Joe%27s_Own_Editor), similaire à Emacs ;
- [Neovim](https://fr.wikipedia.org/wiki/Neovim), un fork de Vim.
