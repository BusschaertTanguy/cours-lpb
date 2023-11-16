# Les expressions et les opérateurs

Ce petit chapitre intermédiaire explique les expressions dans JS. Ceci est assez important a comprendre, pour savoir l'ordre dans lequel JS lit une ligne de code.

Une expression est une unite de code valide qui est résolu en une valeur.

Il y a 2 types d'expressions.

Le premier est celle qui a un effet de bord (il y a eu un changement), par exemple

```js
x = 7
```

Est une expression qui utilise l’opérateur `=` pour assigner la valeur `7` a la variable `x`. L'effet de bord ici est que la valeur de `x` a change.

Le deuxième est une expression purement évalué, ceci veut dire que elle n'a pas d'effet de bord (rien a change), par exemple

```js
3 + 4
```

Cette expression utilise l’opérateur `+` pour ajouter `3` a `4`, et produit donc la valeur `7`. Si cette valeur n'est pas assigner a une variable, il ne se passe rien et elle est écartée.

Nous pouvons donc combiner un expression avec effet de bord, avec une expression purement évalue, par exemple

```js
x = 3 + 4
```

La partie `3 + 4` est l'expression évalue qui va produire la valuer `7`, puis cette valeur est utiliser dans une expression avec effet de bord: `x = 7`.

Pourquoi est-ce important de comprendre les expressions ? Parce que il y a un ordre d'execution quand nous combinons des expressions. Ceci est nomme la 'précédence des opérateurs'. Ce concept est aussi connu dans notre monde, par exemple dans les maths.

Quand nous avons une operations de maths: `7 + 3 * 2`, nous avons appris que la multiplication a priorité sur l'addition. Dans ce cas si, l’opérateur `*` a une plus haute precedence que l’opérateur `+`.

Quand nous définissons une expression, celle si peut contenir plusieurs opérateurs, dans notre exemple precedent

```js
x = 3 + 4
```

Pourquoi est-ce que l'expression `3 + 4` est évalue avant `x = 3` ? Tout simplement parce que notre opérateur `+` a une plus haute precedence que l’opérateur `=`.

Nous devons d’abord donc résoudre `3 + 4`, et puis seulement apres assigner le résultat de cette operation a `x`

Il y a une liste complete qui explique la precedence de tous les opérateurs de JS [ici](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Operator_precedence#tableau).

Celle si est assez complex pour un debutant, pour le moment, sachez que l’opérateur `=` a une precedence tres basse de '2', et que nos opérateurs mathématiques / logiques ont une precedence de '9' est plus, ce qui explique pourquoi la partie a droite de `=` est évalue en premier.