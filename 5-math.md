# L'objet Math

L'objet natif (inclus par défaut dans JS) `Math`, et un regroupement de constantes et de fonctions mathématiques.

La documentation de cet objet peut être trouver [ici](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Math).

Nous allons voire quelque exemple de quelque fonctions utilisées fréquemment.

```js
let valeurNegative = -5;
let valeurDecimal = 10.23;

let abs = Math.abs(valeurNegative); // 5, nous rend la valeur absolue
let floor = Math.floor(valeurDecimal); // 10, nous rend un entier arrondi vers le bas (floor = sol)
let ceil = Math.ceil(valeurDecimal); // 11, nous rend un entier arrondi vers le haut (ceil = plafond)
let round = Math.round(valeurDecimal); // 10, nous rend un entier arrondi vers l'entier le plus proche
let random = Math.random(); // Nous rend un nombre entre 0 et 1 (1 exclu).
```

Voici une façons de générer un decimal `x` dans un interval `min` (inclus) et `max` (exclus).

```js
let min = 10;
let max = 400;
let x = Math.random() * (max - min) + min;
```

Suivant le precedence, le calcul est:
- max - min => 390
- Chiffre entre 0..1 * 390 = chiffre entre 0 (inclus) et 390 (exclus)
- Chiffre 0..390 + min => chiffre entre 10.400

Voici une façons de générer un entier `x` dans un interval `min` (inclus) et `max` (exclus), qui est donc un extension de notre formule précédente.

```js
let min = 10;
let max = 400;

min = Math.ceil(min);
max = Math.floor(max);
let x = Math.floor(Math.random() * (max - min)) + min;
```

La logique est équivalente, sauf que:
- nous bridons le min et max vers un entier grace a `ceil` et `floor`.
- avant notre dernier `+ min`, nous bridons le résultat de notre random et les limites vers un entier grace a `floor`

Voici une façons de générer un entier `x` dans un interval `min` (inclus) et `max` (inclus), qui est donc un extension de notre formule précédente.

```js
let min = 10;
let max = 400;

min = Math.ceil(min);
max = Math.floor(max);
let x = Math.floor(Math.random() * (max - min + 1)) + min;
```

La logique est équivalente, sauf que:
- pour que la limite max soit inclus, il nous suffi d'ajouter un + 1 dans notre partie `max - min`