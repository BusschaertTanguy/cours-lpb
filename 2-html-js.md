# Écrire du HTML a partir de JS

JS par défaut a ete créé pour rendre nos pages HTML dynamiques.

Pour nos exercices, il nous faut une façons de voir nos résultats sur notre écran.

Sans trop approfondir dans le detail de cette méthode, nous allons utiliser l'objet `document` pour interagir avec notre page web.

Dans JS, quand notre script est lu par notre navigateur, une façons d'ajouter de contenu a notre page est grace a la fonction `write` qui se trouve sur l'objet `document`.

Il nous suffit de passer une chaîne de caractères contenant le HTML que l'ont veut afficher, par exemple.

```js
document.write("<b>Bonjour, le monde!</b>");
```

Va ajouter le texte "Bonjour, le monde!" a notre page, avec des balises `<b></b>`, qui va afficher notre texte en gras.

Quand nous faisons nos exercices en JS, nous allons donc utiliser cette méthode pour communiquer nos résultats sur l’écran.