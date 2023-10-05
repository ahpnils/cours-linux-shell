# Chapitre 4 : les alias

## Usage et définitions

Assez vite on se rend compte qu'on utilise souvent les mêmes options pour les
commandes les plus utilisées. On peut aussi vouloir que certaines options
deviennent "par défaut", pour implémenter par exemple des garde-fous (`rm -i`).

Les alias sont un moyen de mettre en place cette personnalisation. Pour définir
un alias, la syntaxe est la suivante :

```
alias macommandecustom='unevraiecommande --unevraieoption --uneautrevraieoptionsionveut'
```

Lancée sans argument, la commande `alias` permet de lister les alias. On peut
aussi lancer la commande `alias monalias` qui ne listera que l'alias demandé,
s'il existe.

On peut aussi supprimer un alias avec la commande `unalias nomdelalias`.

Enfin, dans le cas où l'alias "remplace" une commande existante (par exemple,
un alias sur `ls` qui le redéfinit en `ls -l`), il est possible de lancer la
commande d'origine (c'est-à-dire, la version non "aliasée") via `\macommande`
(donc `\ls` pour notre exemple sur `ls`).

Attention ! Ainsi défini, l'alias n'est valable que dans le shell courant, pour
la session courante. Une fois la session fermée, l'alias est perdu. Il est
cependant possible d'avoir des alias en permanence dans ses sessions en les
ajoutant au fichier `~/.bashrc` ou `~/.bash_profile`. L'édition de fichiers
texte sera abordée dans le prochain chapitre.

## Exercice

GameShell, niveau 14.
