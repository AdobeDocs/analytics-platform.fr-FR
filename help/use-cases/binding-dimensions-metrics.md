---
title: Utilisation de dimensions et de mesures de liaison dans CJA
description: Attribuer des dimensions à des tableaux d’objets pour une analyse de persistance complexe.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
source-git-commit: 4381a01b072084701d065d7f41de539412c8d371
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 1%

---

# Utilisation de dimensions et de mesures de liaison dans CJA

Customer Journey Analytics propose plusieurs méthodes pour conserver les valeurs de dimension au-delà de l’accès sur lequel elles sont définies. L’une des méthodes de persistance qui Adobe les offres est connue sous le nom de liaison. Dans les versions précédentes d’Adobe Analytics, ce concept était connu sous le nom de marchandisage.

Bien que vous puissiez utiliser des dimensions de liaison avec des données d’événement de niveau supérieur, ce concept est préférable lorsque vous utilisez des [Tableaux d’objets](object-arrays.md). Vous pouvez attribuer une dimension à une partie d’un tableau d’objets sans l’appliquer à tous les attributs d’un événement donné. Vous pouvez, par exemple, attribuer un terme de recherche à un produit du tableau d’objets de panier sans lier ce terme à l’événement entier.

## Exemple 1 : Utilisation de dimensions de liaison pour attribuer des attributs de produit supplémentaires à un achat

Vous pouvez lier les éléments de dimension d’un tableau d’objets à une autre dimension. Lorsque l’élément de dimension lié apparaît, CJA rappelle la dimension liée et l’inclut dans l’événement pour vous. Tenez compte du parcours client suivant :

1. Un visiteur affiche la page d’un produit sur un lave-linge.

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. Le visiteur affiche ensuite une page produit sur un sèche-linge.

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. Finalement, ils font un achat. La couleur de chaque produit n’a pas été incluse dans l’événement d’achat.

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

Si vous souhaitez consulter les recettes par couleur sans dimension de liaison, la dimension `product.color` persiste et attribue incorrectement le crédit à la couleur du sèche-linge :

| product.color | chiffre d’affaires |
| --- | --- |
| néon orange | 2099 |

Vous pouvez accéder au Gestionnaire de vues de données et lier la couleur du produit au nom du produit :

![Dimension de liaison](assets/binding-dimension.png)

Lorsque vous définissez ce modèle de persistance, Adobe prend note du nom du produit chaque fois que la couleur du produit est définie. Lorsqu’il reconnaît le même nom de produit dans un événement ultérieur pour ce visiteur, la couleur du produit est également ajoutée. Les mêmes données lorsque vous liez la couleur du produit au nom du produit ressemblent à ce qui suit :

| product.color | chiffre d’affaires |
| --- | --- |
| blanc | 1 600 |
| néon orange | 499 |

## Exemple 2 : Utilisation de mesures de liaison pour lier un terme de recherche à un achat de produit

L’une des méthodes de marchandisage les plus courantes d’Adobe Analytics a été de lier un terme de recherche à un produit afin que chaque terme de recherche reçoive du crédit pour son produit approprié. Tenez compte du parcours client suivant :

1. Un visiteur arrive sur votre site et recherche &quot;gants de boxe&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. Ils trouvent une paire de gants qu&#39;ils aiment, et l&#39;ajoutent à leur panier.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. Le visiteur recherche ensuite &quot;raquette de tennis&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. Ils trouvent une raquette qu&#39;ils aiment, et l&#39;ajoutent à leur panier.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. Le visiteur recherche une troisième fois &quot;chaussures&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. Ils trouvent une paire de chaussures qu&#39;ils aiment, et l&#39;ajoutent à leur panier.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. Le visiteur passe par le processus de passage en caisse et achète ces trois éléments.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

Si vous utilisez un modèle d’attribution traditionnel avec un terme de recherche, les trois produits attribuent des recettes à un seul terme de recherche. Par exemple, si vous avez utilisé la première attribution avec la dimension de terme de recherche :

| search_term | chiffre d’affaires |
| --- | --- |
| gants de boxe | 204,97 $ |

Si vous avez utilisé la dernière attribution avec la dimension de terme de recherche, les trois produits attribuent toujours des recettes à un seul terme de recherche :

| search_term | chiffre d’affaires |
| --- | --- |
| chaussures | 204,97 $ |

Bien que cet exemple ne concerne qu’un seul visiteur, de nombreux visiteurs qui recherchent des éléments différents peuvent attribuer des termes de recherche à différents produits, ce qui rend difficile de déterminer les meilleurs résultats de recherche.

Avec une dimension de liaison, Adobe prend note de l’élément de dimension auquel il est lié. Lorsque cette même valeur de liaison est affichée dans un événement ultérieur, elle fait passer l’élément de dimension afin que vous puissiez lui attribuer la mesure souhaitée. Dans cet exemple, nous pouvons définir la dimension de liaison de search_term sur le nom du produit. Lorsque nous définissons cette dimension dans le gestionnaire des vues de données, nous devons également définir une mesure de liaison, car la dimension de liaison se trouve dans un tableau d’objets. Une mesure de liaison agit comme un déclencheur pour une dimension de liaison. Elle se lie donc uniquement aux événements dans lesquels la mesure de liaison est présente. Dans cet exemple d’implémentation, la page des résultats de recherche inclut toujours une dimension de terme de recherche et une mesure de recherche. Nous pouvons lier les termes de recherche au nom du produit chaque fois que la mesure Recherches est présente.

![Mesure de liaison](assets/binding-metric.png)

La définition de la dimension du terme de recherche sur ce modèle de persistance exécute la logique suivante :

* Lorsque search_term se trouve dans un événement, recherchez la présence du nom du produit.
* Si le nom du produit n’est pas présent, ne faites rien.
* Si le nom du produit est présent, vérifiez la présence de la mesure Recherches .
* Si la mesure Recherches n’est pas présente, ne faites rien.
* Si la mesure Recherches est présente, liez le terme de recherche à tous les noms de produits. Il agit comme s’il se trouvait au même niveau que le nom du produit pour cet événement. Dans cet exemple, il est traité comme product.search_term.
* Si le même nom de produit s’affiche dans un événement consécutif, le terme de recherche lié existe également.

Dans Analysis Workspace, le rapport résultant ressemble à ce qui suit :

| search_term | chiffre d’affaires |
| --- | --- |
| gants de boxe | 89,99 $ |
| raquette de tennis | 34,99 $ |
| chaussures | 79,99 $ |
