---
title: Utilisation de dimensions et de mesures de liaison dans CJA
description: Attribuez des dimensions aux tableaux dʼobjets et effectuez ainsi une analyse poussée de la persistance.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 38c10e395b816d812d30f0698dc821ee0ea5c9b1
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 75%

---

# Utilisation de dimensions et de mesures de liaison dans CJA

Customer Journey Analytics offre plusieurs façons de conserver les valeurs de dimension au-delà de lʼaccès sur lequel elles sont définies. Adobe offre plusieurs méthodes de persistance, dont la méthode Liaison. Dans les versions précédentes dʼAdobe Analytics, ce concept était connu sous le nom de marchandisage.

Bien que vous puissiez utiliser les dimensions de liaison avec les données dʼévénement de premier niveau, ce concept se prête mieux à une utilisation avec les [Tableaux dʼobjets](object-arrays.md). Vous pouvez attribuer une dimension à une partie dʼun tableau dʼobjets, sans lʼappliquer à tous les attributs dʼun événement donné. Par exemple, vous pouvez attribuer un terme de recherche à un produit de votre tableau dʼobjets de panier sans lier ce terme de recherche à lʼévénement entier.

## Exemple 1 : Utilisation de dimensions de liaison pour attribuer des attributs de produit supplémentaires à un achat

Vous pouvez lier les éléments de dimension d’un tableau d’objets à une autre dimension. Lorsque l’élément de dimension lié apparaît, CJA rappelle la dimension liée et l’inclut dans l’événement pour vous. Prenons lʼexemple de parcours client suivant :

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

Lʼune des méthodes de marchandisage les plus courantes dans Adobe Analytics consiste à lier un terme de recherche à un produit, afin que chaque terme de recherche soit crédité pour le produit approprié. Prenons lʼexemple de parcours client suivant :

1. Un visiteur arrive sur votre site et recherche des « gants de boxe ».

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

1. Il trouve une paire de gants à son goût et lʼajoute au panier.

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

1. Le visiteur recherche ensuite une « raquette de tennis ».

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

1. Il trouve une raquette qui lui plaît et lʼajoute au panier.

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

1. Le visiteur effectue une troisième recherche, qui porte cette fois sur des « chaussures ».

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

1. Il trouve la paire de chaussures de ses rêves et lʼajoute au panier.

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

1. Le visiteur suit le processus de passage en caisse et effectue lʼachat de ces trois articles.

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

Si vous utilisez un modèle dʼattribution traditionnel avec une dimension Terme de recherche, les trois produits attribuent le chiffre dʼaffaires à un seul terme de recherche. Par exemple, si vous avez utilisé la première attribution avec la dimension Terme de recherche :

| search_term | chiffre d’affaires |
| --- | --- |
| gants de boxe | 204,97 USD |

Si vous avez utilisé la dernière attribution avec la dimension Terme de recherche, les trois produits attribuent toujours le chiffre dʼaffaires à un seul terme de recherche :

| search_term | chiffre d’affaires |
| --- | --- |
| chaussures | 204,97 USD |

Bien que cet exemple ne concerne quʼun seul visiteur, de nombreux visiteurs qui recherchent des choses différentes peuvent attribuer à tort des termes de recherche à différents produits, ce qui rend difficile la détermination des meilleurs résultats de recherche.

Dans le cas dʼune dimension de liaison, Adobe tient compte de lʼélément de dimension auquel elle est liée. Lorsque cette même valeur de liaison apparaît dans un événement ultérieur, elle fait apparaître lʼélément de dimension afin que vous puissiez lui attribuer la mesure souhaitée. Dans cet exemple, nous pouvons définir la dimension de liaison de search_term sur le nom du produit. Lorsque nous définissons cette dimension dans le gestionnaire Vue de données, nous devons également définir une mesure de liaison, car la dimension de liaison se trouve dans un tableau dʼobjets. Une mesure de liaison agit comme un déclencheur pour une dimension de liaison, de sorte quʼelle ne se lie que sur les événements où la mesure de liaison est présente. Dans cet exemple dʼimplémentation, la page de résultats de recherche comprend toujours une dimension Terme de recherche et une mesure Recherches. Nous pouvons lier les termes de recherche au nom du produit lorsque la mesure Recherches est présente.

![Mesure de liaison](assets/binding-metric.png)

La définition de la dimension Terme de recherche sur ce modèle de persistance exécute la logique suivante :

* Lorsque search_term est dans un événement, vérifiez la présence du nom du produit.
* Si le nom du produit nʼest pas présent, ne faites rien.
* Dans le cas contraire, vérifiez la présence de la mesure Recherches.
* Si la mesure Recherches nʼest pas présente, ne faites rien.
* Dans le cas contraire, liez le terme de recherche à tous les noms de produits. Elle agit comme si elle était au même niveau que le nom du produit pour cet événement. Dans cet exemple, elle est traitée comme product.search_term.
* Si le même nom de produit est vu dans un événement ultérieur, le terme de recherche lié y existe également.

Dans Analysis Workspace, le rapport obtenu ressemble à ce qui suit :

| search_term | chiffre d’affaires |
| --- | --- |
| gants de boxe | 89,99 USD |
| raquette de tennis | 34,99 USD |
| chaussures | 79,99 USD |
