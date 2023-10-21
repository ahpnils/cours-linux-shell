# Chapitre 19 : les liens symboliques

Sous Unix et Linux, il n'y a pas de raccourcis. À la place, il y a des liens
symboliques. Le but est fonctionnellement le même, rendre accessible un fichier
ou un répertoire depuis un autre emplacement.

Il existe des liens non-symboliques, appelés aussi "liens durs", mais ils ne
font pas l'objet de ce chapitre.

Pour créer un lien symbolique, on utilise la commande `ln`, avec
obligatoirement l'argument `-s`.

## Exercice

Créer l'arborescence d'exercice via la commande `mkdir -vp
~/Documents/Exercices/{foo,bar}/`.

Créer un fichier `foo.txt` via la commande `echo "foo" >
~/Documents/Exercices/foo/foo.txt`

Créer un lien symbolique nommé `bar.txt` dans le répertoire
`~/Documents/Exercices/bar/`, qui renvoit vers `foo.txt` : `ln -s
~/Documents/Exercices/foo/foo.txt ~/Documents/Exercices/bar/bar.txt`.

Utiliser la commande `ls -l` dans le répertoire `~/Documents/Exercices/bar/`,
puis afficher avec `cat` le contenu du lien symbolique `bar.txt`.

Ajouter du contenu à `foo.txt` : `echo bar >> ~/Documents/Exercices/foo/foo.txt`,
puis examiner le contenu du fichier et du lien symbolique avec `cat`.

Effacer le lien symbolique à l'aide de la commande `rm`, puis vérifier la
présence du fichier `foo.txt`, ainsi que son contenu. Recréer ensuite le lien
symbolique selon la consigne en début d'exercice.

Effacer maintenant le fichier `foo.txt`, puis vérifier la présence du lien
symbolique et son contenu. Recréer un fichier `foo.txt` comme en début
d'exercice mais contenant cette fois-ci le mot "baz". Vérifier ensuite la
présence du lien symbolique et son contenu.

Questions :

* quelles sont les particularités visibles d'un lien symbolique ?
* quel est le contenu du lien symbolique ? Suit-il celui du fichier d'origine ?
* est-ce que la suppression d'un lien symbolique a un impact sur le fichier
  d'origine ?
* est-ce que la suppression du fichier d'origine a un impact sur le lien
  symbolique ?

