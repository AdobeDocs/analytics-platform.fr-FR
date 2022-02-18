---
title: Utilisation de dimensions et de mesures de liaison dans CJA
description: Attribuez des dimensions aux tableaux dʼobjets et effectuez ainsi une analyse poussée de la persistance.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 419279f8e01bc81b17c372c6c53939b81ddbf4b7
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 36%

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

Lorsque vous définissez ce modèle de persistance, CJA prend note du nom du produit chaque fois que la couleur du produit est définie. Lorsqu’il reconnaît le même nom de produit dans un événement ultérieur pour ce visiteur, la couleur du produit est également ajoutée. Les mêmes données lorsque vous liez la couleur du produit au nom du produit ressemblent à ce qui suit :

| product.color | chiffre d’affaires |
| --- | --- |
| blanc | 1 600 |
| néon orange | 499 |

## Exemple 2 : Utilisation de mesures de liaison pour lier un terme de recherche à un achat de produit

Lʼune des méthodes de marchandisage les plus courantes dans Adobe Analytics consiste à lier un terme de recherche à un produit, afin que chaque terme de recherche soit crédité pour le produit approprié. Prenons lʼexemple de parcours client suivant :

1. Un visiteur arrive sur votre site et recherche des « gants de boxe ». La mesure Recherches est incrémentée d’une unité, et les trois premiers résultats de recherche s’affichent.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
           },
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Professional gloves",
           }
       ]
   }
   ```

2. Il trouve une paire de gants à son goût et lʼajoute au panier.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           }
       ]
   }
   ```

3. Le visiteur recherche ensuite une « raquette de tennis ». La mesure Recherches est incrémentée d’une unité, et les trois premiers résultats de recherche s’affichent.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Women's open racket",
           },
           {
               "name": "Extreme racket",
           }
       ]
   }
   ```

4. Il trouve une raquette qui lui plaît et lʼajoute au panier.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           }
       ]
   }
   ```

5. Le visiteur effectue une troisième recherche, qui porte cette fois sur des « chaussures ». La mesure Recherches est incrémentée d’une unité, et les trois premiers résultats de recherche s’affichent.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
           },
           {
               "name": "Tennis shoes",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

6. Il trouve la paire de chaussures de ses rêves et lʼajoute au panier.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

7. Le visiteur suit le processus de passage en caisse et effectue lʼachat de ces trois articles.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "price": "79.99"
           }
       ]
   }
   ```

Si vous utilisez un modèle d’attribution qui n’inclut pas de dimension de liaison avec un terme de recherche, les trois produits n’attribuent des recettes qu’à un seul terme de recherche. Par exemple, si vous avez utilisé l’affectation initiale avec la dimension du terme de recherche :

| search_term | chiffre d’affaires |
| --- | --- |
| gants de boxe | 204,97 USD |

Si vous avez utilisé l’attribution Le plus récent avec la dimension du terme de recherche, les trois produits attribuent toujours des recettes à un seul terme de recherche :

| search_term | chiffre d’affaires |
| --- | --- |
| chaussures | 204,97 USD |

Bien que cet exemple ne concerne quʼun seul visiteur, de nombreux visiteurs qui recherchent des choses différentes peuvent attribuer à tort des termes de recherche à différents produits, ce qui rend difficile la détermination des meilleurs résultats de recherche.

CJA détecte automatiquement la relation entre la dimension sélectionnée et la dimension de liaison. Si la dimension de liaison se trouve dans un tableau d’objets alors que la dimension sélectionnée se trouve à un niveau supérieur, une mesure de liaison est requise. Une mesure de liaison agit comme un déclencheur pour une dimension de liaison, de sorte quʼelle ne se lie que sur les événements où la mesure de liaison est présente.

Dans cet exemple dʼimplémentation, la page de résultats de recherche comprend toujours une dimension Terme de recherche et une mesure Recherches. Nous pouvons lier les termes de recherche au nom du produit lorsque la mesure Recherches est présente.

![Mesure de liaison](assets/binding-metric.png)

La définition de la dimension Terme de recherche sur ce modèle de persistance exécute la logique suivante :

* Lorsque la dimension du terme de recherche est définie, vérifiez la présence du nom du produit.
* Si le nom du produit nʼest pas présent, ne faites rien.
* Dans le cas contraire, vérifiez la présence de la mesure Recherches.
* Si la mesure Recherches nʼest pas présente, ne faites rien.
* Si la mesure Recherches est présente, liez le terme de recherche à tous les noms de produits de cet événement. Il se copie lui-même au même niveau que le nom du produit pour cet événement. Dans cet exemple, elle est traitée comme product.search_term.
* Si le même nom de produit est affiché dans un événement ultérieur, le terme de recherche lié est également transféré vers cet événement.

Dans Analysis Workspace, le rapport obtenu ressemble à ce qui suit :

| search_term | chiffre d’affaires |
| --- | --- |
| gants de boxe | 89,99 USD |
| raquette de tennis | 34,99 USD |
| chaussures | 79,99 USD |

## Exemple 3 : Liaison du terme de recherche vidéo au profil utilisateur

Vous pouvez lier un terme de recherche à un profil utilisateur afin que la persistance entre les profils reste complètement séparée. Par exemple, votre entreprise exécute un service de diffusion en continu où un compte peut avoir plusieurs profils. Le visiteur dispose d’un compte enfant et d’un compte adulte.

1. Le compte se connecte sous le compte enfant et recherche une émission télévisée pour enfants. Notez que la variable `"AccountID"` is `2` pour représenter le profil enfant.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "2",
       "Searches": "1",
       "search_term": "kids TV show"
   }
   ```

1. Ils trouvent l&#39;émission &quot;Orangey&quot; et la jouent pour que leur enfant puisse la regarder.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

1. Plus tard dans la soirée, le parent passe à son profil et recherche du nouveau contenu pour adultes à regarder. Notez que la variable `"AccountID"` is `1` pour représenter le profil d’adulte. Les deux profils appartiennent au même compte, représenté par le même `"PersonID"`.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "1",
       "Searches": "1",
       "search_term": "inappropriate adult movie"
   }
   ```

1. Ils ont trouvé le spectacle &quot;Game of Dethrones&quot; et ont passé leur soirée à le regarder.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "1",
       "ShowName": "Game of Dethrones",
       "VideoStarts": "1"
   }
   ```

1. Le lendemain, ils ont continué l&#39;émission &quot;Orangey&quot; pour leur enfant. Ils n&#39;ont pas besoin de chercher, puisqu&#39;ils sont déjà au courant de l&#39;émission.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

Si vous utilisez un modèle d’attribution sans dimension de liaison, la variable `"inappropriate adult movie"` le terme &quot;recherche&quot; est attribué à la dernière vue de l&#39;émission télévisée destinée aux enfants. Cependant, si vous avez lié `search_term` to `AccountID`, les recherches de chaque profil sont isolées dans leur propre profil, attribuée aux affichages corrects qu’ils recherchent.

## Exemple 4 : Évaluation du comportement de navigation et de recherche dans un paramètre de vente au détail

1. Un visiteur effectue une recherche pour `"camera"`. Notez qu’aucun produit n’est défini sur cette page.

   ```json
   {
       "search_term": "camera",
       "product_finding_method": "search"
   }
   ```

1. Ils cliquent sur une caméra qu&#39;ils aiment et l&#39;ajoutent au panier.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. Le visiteur accède ensuite à la catégorie ceinture pour homme sans effectuer de recherche. Notez qu’aucun produit n’est défini sur cette page.

   ```json
   {
       "category": "Men's belts",
       "product_finding_method": "browse"
   }
   ```

1. Ils cliquent sur la mention de leur choix et l’ajoutent au panier.

   ```json
   {
       "Product": [
           {
               "name": "Ratchet belt"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. Ils passent par le processus de passage en caisse et achètent ces deux articles.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera",
               "price": "399.99"
           },
           {
               "name": "Ratchet belt",
               "price": "19.99"
           }
       ],
       "Purchase": "1"
   }
   ```

Si la persistance est définie sur l’allocation la plus récente sans dimension de liaison, la totalité des 419,98 $ de recettes est attribuée à la variable `browse` méthode de recherche. Si la persistance est définie à l’aide de l’allocation d’origine sans dimension de liaison, l’ensemble des 419,98 $ de recettes est attribué à la variable `search` méthode de recherche.

Cependant, si vous liez `product_finding_method` Pour la mesure Ajouts au panier , le rapport résultant attribue chaque produit à la méthode de recherche correcte.

| Méthode de recherche de produit | Recettes |
| --- | --- |
| search | 399,99 |
| parcourir | 19,99 |
