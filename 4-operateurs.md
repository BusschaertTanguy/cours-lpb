# L’opérateur d'assignement 

L’opérateur assignement permet de définir une valeur a une variable

```js
let x = 5;
```

- L'opérateur `=` a une precedence de `2`, et une associativité de droite a gauche.

# Les opérateurs arithmétiques

Les opérateurs arithmétiques combine 2 operands numérique, renvoyant aussi une valeur numérique.

```js
let addition = 3 + 4;         // 7
let soustraction = 4 - 3;     // 1
let multiplication = 4 * 3;   // 12
let division = 8 / 2;         // 4
let reste = 10 % 3;           // 1, envoie le reste d'une division entier
let puissance = 3 ** 3;       // 27
```

- Les opérateurs `+` et `-` ont une precedence de `12`, et une associativité de gauche a droite.
- Les opérateurs `*`, `/` et `%` ont une precedence de `13`, et une associativité de gauche a droite.
- L'opérateur `**`a une precedence de `14`, et une associativité de droite a gauche.

# Les opérateurs de comparaison

Les opérateurs de comparaison compare ses operands, et renvoie une valeur booléen (vrai / faux). Des nombres, chaines, booléennes et objets peuvent être comparées.

Si les 2 operands ne sont pas du meme type, JS va essaye de les convertir dans un type approprié.

```js
let egalite1 = 3 == 3;          // Vrai
let egalite2 = 3 == "3";        // Vrai, JS converti notre nombre en chaîne

let inegalite = 3 != 4;         // Faux

let superieurStricte1 = 4 > 3;  // Vrai
let superieurStricte2 = 3 > 4;  // Faux
let superieur = 3 >= 3;         // Vrai

let inferieurStricte1 = 4 < 3;  // Faux
let inferieurStricte2 = 3 < 4;  // Vrai
let inferieur = 3 <= 3;         // Vrai
```

Il y a 2 opérateurs exceptionnels, qui ne vont pas convertir les types des valeurs si il ne sont pas égal, mais qui va aussi regarder que le type soit le meme.

```js
let egaliteStricte1 = 3 === 3;      // Vrai
let egaliteStricte2 = 3 === "3";    // Faux, les types ne sont pas le meme

let inegaliteStricte1 = 3 !== 3;      // Faux
let inegaliteStricte2 = 3 !== "3";    // Vrai, les types ne sont pas le meme
```

- Les opérateurs `==`, `===`, `!=`, `!==`  ont une precedence de `9`, et une associativité de gauche a droite.

- Les opérateurs `<`, `<=`, `>`, `>=`  ont une precedence de `10`, et une associativité de gauche a droite.

# Les opérateurs logiques

Les opérateurs de logiques sont généralement utilisés avec des valeurs booléennes. Il y a 2 cas a comprendre avec les opérateurs logiques: Les operands sont tous des valeurs booléennes OU ils ne sont pas tous des valeurs booléennes.

Il y a 3 opérateurs de logiques:
- `operand 1 && operand 2` correspond a ET
- `operand 1 || operand 2` correspond a OU
- `!operand` correspond a NON

**Tous les operands sont des valeurs booléennes**

Si toutes les valeurs sont des booléennes, les opérateurs ont la logique suivante:

- ET: Retourne la valeur `true` si nos 2 operands sont `true`, sinon retourne `false`

L’opérateur `&&` a une precedence de `5`, et une associativité de gauche a droite.

```js
let a = true;
let b = true;
let c = false;

let resultat1 = a && b;         // True
let resultat2 = a && c;         // False
let resultat3 = a && b && c;    // False, associativité gauche a droite, d’abord a && b, puis apres && c.
```

- OU: Retourne la valeur `true` si un de nos 2 operands est `true`, sinon retourne `false`

L’opérateur `||` a une precedence de `4`, et une associativité de gauche a droite.

```js
let a = true;
let b = true;
let c = false;
let d = false;

let resultat1 = a || b;         // True
let resultat2 = a || c;         // True
let resultat3 = c || d;         // False
let resultat4 = a || b || c;    // True, associativité gauche a droite, d’abord a && b, puis apres && c.
```

- NON: Retourne la valeur inverse de notre booléen. (`false` si notre valeur est `true`, et inversement).

L’opérateur `!` a une precedence de `15`, et une associativité de droite a gauche.

```js
let a = true;
let b = false

let resultat1 = !a; // False
let resultat2 = !b; // True
```

Il est important de connaître la precedence et l'associativité de nos opérateurs logique, pour savoir les combines.

Notre ET a une plus grande precedence que notre OU, donc quand nous avons un enchaînement qui contient les 2, il faut d’abord faire les ET.


```js
let a = true;
let b = false;
let c = true;

let resultat = a && b || c; // True, d'abord a && b, qui nous rend false, puis apres || c.
```

Il est possible de soit meme gérer l'ordre de comparaison, grace a l'opérateur `()`. Cette opérateur a la plus grande precedence de tout les opérateurs, elle est de `19`. Nous pouvons isoler une expression dans `()`, pour que elle a une precedence plus haute. Dans notre exemple precedent

```js
let a = true;
let b = false;
let c = true;

let resultat = a && (b || c); // True, mais grace aux (), b || c est évalué en premier. Puis seulement apres le && a/ 
```

**Tous les operands ne sont pas des valeurs booléennes**

Il est possible d'utiliser les opérateurs de logique avec des valeurs non-booléennes, qui peuvent être convertie en valeurs booléennes.

En JS, les valeurs suivantes:
- `null`
- `0`
- `NaN`
- `""` / `''`
- `undefined`

peuvent être convertie en `false`, sinon elle est convertie en `true`.

Ceci est faut automatiquement quand nous utilisons un opérateur de logique avec des valeurs non booléennes.

Dans se cas si, les opérateurs ont la logique suivante:

- ET: Si le premier operand peut être convertie en `false`, renvoie le, sinon renvoie le 2eme operand.

```js
let animal1 = "Chien";
let animal2 = "Chat";
let animal3 = "";

let choix1 = animal1 && animal2; // Choix contient "Chat", parce que notre premier operand n'est pas equivalent a false.
let choix2 = animal3 && animal2; // Choix contient "", parce que notre premier operand est equivalent a false.
```

- OU: Si le premier operand peut être convertie en `true`, renvoie le, sinon renvoie le 2eme operand.

```js
let animal1 = "Chien";
let animal2 = "Chat";
let animal3 = "";

let choix1 = animal1 && animal2; // Choix contient "Chien", parce que notre premier operand n'est pas equivalent a false.
let choix2 = animal3 && animal2; // Choix contient "Chat", parce que notre premier operand est equivalent a false.
```

- NON: Renvoie `false` si l'operand peut être converti en `true`, sinon renvoie `false`.

```js
let animal1 = "Chien";
let animal2 = "";

let non1 = !animal1; // False, animal1 est converti en true.
let non2 = !animal2; // True, animal2 est converti en false.
```