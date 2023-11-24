# Le contrôle de flux

JS nous permet d'executer certaines partie de code seulement is une condition est vrai/fausse. Cette gestion est appeler le contrôle du flux du programme.

# Les blocs d'instructions

Un instruction est 1 ou plusieurs expressions qui finissent par un `;`.

Voici plusieurs exemples d'instructions

```js
let x = 5;
let y = 6 < 7 ;
```

Un bloc d'instruction est 1 ou plusieurs instructions, regrouper par des accolades.

```js
let x = 3;
let y = 4;

// Un premier bloc d'instruction
{
    let a = 10;
    let b = a + 5; // 15
}

// Un deuxième bloc d'instruction
{
    let a = 4;
    let b = a - x; // 1

    let y = 5;
    let c = 10 - y; // 5
}
```

Un bloc d'instruction en soit n'a pas beaucoup de valeur ajoute, a part l'isolement de nos variables définie avec `let` ou `const`.

Comme deja dit dans le chapitre precedent, un variable `let` ou `const` n'est valide que dans sont propre bloc ou un bloc enfant. Dans notre exemple, `a` et `b` sont connu que dans leur propre bloc. `x` est une variable définie 1 niveau plus haut que les 2 blocs, donc elle est bien accessible.

Dans notre 2eme bloc, nous définissons une variable `y` qui existe aussi dans le bloc parent. Il est possible de redéfinir les variables dans un bloc enfant, et dans se bloc la variable la "plus proche" serra utilisée.

Les bloc d'instruction ont beaucoup plus d’utilité quand nous pouvons par exemple les executer que a une certaine condition.

# Les instructions conditionnelles

Une instruction conditionnelle est un ensemble d'instruction (un bloc p.e.) qui est exécutée seulement si une condition logique est vérifiée.

L'instruction `if(expression)` nous permet d'executer un bloc d'instruction si notre expression est vérifie.

```js
let age = 15;

// age < 18 nous renvoie vrai, donc le bloc accroche au if est execute.
if(age < 18) {
    console.log("Je suis mineur.");
}
```

```js
let age = 30;

// age < 18 nous renvoie faux, donc le bloc accroche au if n'est pas execute.
if(age < 18) {
    console.log("Je suis mineur.");
}
```

Optionnellement, il est possible d'ajouter une instruction `else` a notre `if(expression)`. Le bloc relie au `else` est donc executer si notre `if` n'est pas execute.

```js
let age = 30;

// age < 18 nous renvoie faux, donc le bloc dans le else est execute
if(age < 18) {
    console.log("Je suis mineur.");
} else {
    console.log("Je suis majeur.");
}
```

Finalement, il est aussi possible de tester plusieurs conditions a la suite des autres.

Il faut toujours commencer avec un `if(expression)`, mais si vous avez encore d'autre condition a tester, `else if(expression)` peut être ajouter pour chaque teste nécessaire.

```js
let age = 15;

// Nos conditions sont évaluée dans l'ordre, et 1 seul condition peut être exécutée. 
if(age < 3) {
    console.log("Je suis un bébé.");
} else if (age < 12) {
    console.log("Je suis un enfant."); // Celle si est exécutée
} else if (age < 18) {
    console.log("Je suis un ado.");
} else {
    console.log("Je suis un adolescent.");
}
```

Quand nous avons une chaîne de `if` / `else if` / `else` qui utilise exclusivement un opérateur d'egalite (`==`), p.e.

```js
let fruit = "Pomme";

if(fruit == "Orange") {
    console.log("Les oranges sont à 60 centimes le kilo.");
} else if (fruit == "Banane") {
    console.log("Les bananes sont à 48 centimes le kilo.")
} else if (fruit == "Pomme") {
    console.log("Les pommes sont à 32 centimes le kilo.")
} else if (fruit == "Poire") {
     console.log("Les poires sont à 50 centimes le kilo.");
} else {
    console.log("Désolé, nous n'avons pas le fruit que vous cherchez.");
}
```

Il est possible de utiliser l'instruction `switch`.

Cette instruction est equivalent a un enchaînement de `if` / `else if` / `else` qui utilisent `==` comme expression.

Nous devons d'abord choisir la variable que nous voulons comparer et la passer a notre instruction `switch`, suivi d'un bloc d'instruction.

pour chaque valeur de comparaison, nous allons créer une "branche" qui a cette forme:

```js
case valeurDeComparaison:
    instruction1;
    instruction2;
    break;
```
La valeur derriere `case` serra celle de comparaison, suivi d'un `:`. Il est possible apres d'ajouter autant de ligne d'instruction que l'on veut. Quand nous arrivons a la fin de notre `case`, il faut le finir avec un `break`, qui nous permet de sortir du `switch` et de ne pas continuer son execution.

Il est aussi possible d'ajouter un cas par default, qui est executer si la valeur ne correspond avec aucun de nos `case`. Celle si ne doit pas contenir de `break` parce que c'est la dernière valeur possible.

Voici notre exemple precedent de `if` / `else if` / `else` avec un `switch`.

```js
let fruit = "Pomme";

switch (fruit) {
  case "Orange":
    console.log("Les oranges sont à 60 centimes le kilo.");
    break;
  case "Banane":
    console.log("Les bananes sont à 48 centimes le kilo.");
    break;
  case "Pomme":
    console.log("Les pommes sont à 32 centimes le kilo.");
    break;
  case "Poire":
    console.log("Les poires sont à 50 centimes le kilo.");
    break;
  default:
    console.log("Désolé, nous n'avons pas le fruit que vous cherchez.");
}
```