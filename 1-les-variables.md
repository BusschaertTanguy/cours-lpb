# Les variables

Les variables sont des conteneurs pour des valeurs, tel un chiffre pour une somme, ou une chaîne de caractères dans un phrase.

La particularité d'une variable c'est que sa valeur peut changer, d'ou le nom variable.

Une variable peut contenir tout type de valeurs:
- Des nombres entier ou decimal
- Des chaines de caractères
- Des objets
- Des tableaux
- Des booleans (true / false)
- Rien (null / undefined)

## Declarer une variable

Avant de pouvoir utiliser une variable, il faut d’abord la créer. Le fait de créer une variable est appeler la "declarer".

```js
let ma_variable;
```

Le mot clef `let`, `var` ou `const` nous permet de declarer une variable. Nous verrons la difference plus tard.

Une variable declarer n'a pas forcement de valeur, pour lui attribuer une value, il faut l'initialiser.

## Initialiser un valeur

Une fois la variable déclarée, on peut lui assigner une valuer, ceci s'appelle "initialiser" la variable.

```js
let ma_variable;
ma_variable = 10;
```

Il est aussi possible de faire la declaration et l'initialisation en 1 ligne

```js
let ma_variable = 10;
```

## let, var et const


La difference entre `let` et `var` est que la variable declarer avec `let` est seulement accessible dans son propre block (ou un block enfant), alors que `var` est aussi accessible en dehors de son block.

Un block est défini par une paire de `{}`. 

```js
let variable_1 = 10;

{
    let variable_2 = 20;
    var variable_3 = 30;

    console.log(variable_1); // Affiche 10
    console.log(variable_2); // Affiche 20
    console.log(variable_3); // Affiche 30
}

console.log(variable_1); // Affiche 10
console.log(variable_2); // Affiche undefined, let n'est plus accessible dans un block parent
console.log(variable_3); // Affiche 30, var est accessible dans un block parent
```

Une variable définie avec `const` n'est est constante, cella veut dire que on ne peut plus changer ca valeur.

```js
let variable_1 = 10;
const variable_2 = 20;

variable_1 = 30; // Pas de problème
variable_2 = 40; // Erreur
```

## Les types de variables

Il est possible de stocker plusieurs types dans les variables

### Les nombres

Les nombres entiers et décimaux sont accepter en tant que valeurs

```js
let nombre_entier = 10;
let nombre_decimal = 12.24;
```

### Les chaines

Les chains sont des mots ou de suites de mots. Pour définir une chaîne il suffit de la mettre entre guillemets (simple ou double).

```js
let nom = 'Dupont'; // Simple
let prenom = "Michel"; // Double
```

Les 2 types de guillemets sont permise, mais il est preferable de choisir 1 style et de rester avec celui si.

Il est possible de combiner des chaines de caractères, grace a l’opérateur `+`

```js
let nom = "Dupont" + " " + "Michel";

console.log(nom); // Affiche 'Dupont Michel'
```

Dans l'exemple precedent, nous avons combiner 3 chaines:
- Le nom de famille
- Un espace
- Le prénom

Si une variable contient un chaîne, il est donc aussi possible d'utiliser celle si

```js
let nomDeFamille = "Dupont";
let prenom = "Michel";
let nom = nomDeFamille + " " + prenom;

console.log(nom); // Affiche 'Dupont Michel'
```

Quand il y a une combinaison de variables et de chaines, il est aussi possible d'utiliser des backticks(\`\`) pour définir la chaîne. Vous pouvez introduire les noms de variables dans votre chaîne grace a `${}`.

```js
let nomDeFamille = "Dupont";
let prenom = "Michel";
let nom = `${nomDeFamille} ${prenom}`;
let salutation = `$Bonjour, ${nom}!`;

console.log(salutation); // Affiche 'Bonjour, Dupont Michel!'
```

Les backticks permettent donc de combiner des variables et des chaines pour former une nouvelle chaîne.

### Les booléens

Les booléens sont des valeurs `true`/`false` (vrai ou faux), et ne peuvent prendre que ses 2 valeurs la.

Elle sont généralement utiliser pour tester des conditions.

```js
let suisJeVivant = true;
let test = 6 > 3; // Est-ce que la valeur 6 est plus grande que 3 -> true
```

### Les tableaux

Les tableaux sont une sequence de valeurs. La sequence est définie entre des crochets, et les valeurs sont séparée par des virgules

```js
let noms = ["Tanguy", "Tamara"]; // Un tableau de chaines
let chiffres = [10, 35, 78]; // Un tableau de chiffres
```

Plus d'informations sur le tableau dans son propre chapitre

### Les objets

Les objects dans JS sont un regroupement de variables, qui sont cohérentes ensemble. Les objets représentent dans beaucoup de cas des objets reel, comme par exemple une personne.

Un objet est défini par une paire de `{}`, qui lui meme contient des paires de clef/valeur, séparées par des virgules.

Une paire clef/valeur correspond donc a une propriété de l'objet, et sa valeur.

Pour notre objet personne, nous pourrons avoir:
- `prenom: "Tanguy" // La clef est 'prenom', la valeur est '"Tanguy"'`  
- `nom: "Busschaert" // La clef est 'nom', la valeur est '"Busschaert"'`  

```js
let personne = {
    prenom: "Tanguy",
    nom: "Busschaert"
};
```

Plus d'informations sur l'objet dans son propre chapitre

## Typage faible
JavaScript est un language faiblement type. Ceci veut dire que nous ne devons jamais définir le type d'une variable, et celui si peut changer au cours de sa vie.

```js
let ma_variable = 10; // Définie en tant que nombre

ma_variable = "Salut" // Mis a jour en tant que chaîne.
```