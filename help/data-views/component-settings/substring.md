---
title: Paramètres des composants de sous-chaîne
description: Utilisez un sous-ensemble d’une chaîne comme éléments de dimension.
solution: Customer Journey Analytics
feature: Data Views
exl-id: a763027e-68f7-4f0a-8082-85db5283c8e3
source-git-commit: 81e04d177596430b6e9d971cb1b157b461524314
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 95%

---

# Paramètres des composants de [!UICONTROL sous-chaîne]

Les paramètres des composants de [!UICONTROL sous-chaîne] vous permettent d’effectuer plusieurs méthodes de manipulation de chaîne pour obtenir les éléments de dimension souhaités dans les rapports.

![Paramètres de sous-chaîne](../assets/substring-settings.png)

La [!UICONTROL sous-chaîne] est disponible uniquement sur les dimensions et est rétroactive aux données auxquelles elle est appliquée. Il s’agit d’une transformation immédiate des données qui se produit avant l’application du filtrage ou d’autres opérations d’analyse.

## À partir de la gauche/de la droite

Prenez une partie d’une chaîne en fonction de sa position au début ou à la fin d’une chaîne. **[!UICONTROL De la gauche]** et **[!UICONTROL À droite]** propose deux listes déroulantes : **[!UICONTROL De]** (où la sortie commence) et **[!UICONTROL À]** (où la sortie se termine).

* **[!UICONTROL Début de chaîne]** : le début de la chaîne.
* **[!UICONTROL Fin de chaîne]** : la fin de la chaîne.
* **[!UICONTROL Position]** : un nombre statique de caractères de la gauche ou de la droite, selon la méthode.
* **[!UICONTROL Chaîne]** : faites correspondre un caractère ou une séquence de caractères pour indiquer le début ou la fin d’une chaîne. Cette liste déroulante propose également d’autres options :
   * **[!UICONTROL Correspondance]** : la chaîne à faire correspondre. Si l’entrée ne correspond pas à ce champ, [Aucune option de valeur](no-value-options.md) ne s’applique.
   * **[!UICONTROL Index]** : le critère **[!UICONTROL Correspondance]** peut être présent plusieurs fois dans une chaîne. Cet entier détermine la correspondance à utiliser pour démarrer ou terminer la sortie, selon la méthode. Par exemple, un index de `1` représente la première correspondance. Si l’index est supérieur au nombre de correspondances disponibles, [Aucune option de valeur](no-value-options.md) ne s’applique.
   * **[!UICONTROL Inclure la chaîne]** : une case à cocher qui inclut la chaîne **[!UICONTROL Correspondance]** dans la sortie si activée.
* **[!UICONTROL Longueur]** : un entier qui spécifie le nombre de caractères à inclure après la position de départ de la sortie. Disponible uniquement sous **[!UICONTROL À]** liste déroulante.

## Délimiteur

Utilisez cette méthode pour les champs qui utilisent un délimiteur pour séparer plusieurs valeurs de chaîne. Vous pouvez extraire un élément individuel à utiliser comme sortie ou convertir la chaîne en élément de schéma de tableau d’objets.

* **[!UICONTROL Critère]** : comment traiter la liste délimitée de valeurs.
   * **[!UICONTROL De la gauche]** : commencez au début de la liste délimitée et comptez vers l’avant.
   * **[!UICONTROL De la droite]** : commencez à la fin de la liste délimitée et comptez à rebours.
   * **[!UICONTROL Convertir en tableau]** : traitez cette dimension comme s’il s’agissait d’un élément de schéma de tableau d’objets.
* **[!UICONTROL Délimiteur]** : le délimiteur utilisé par le champ.
* **[!UICONTROL Index]** : uniquement présent si le critère est De la gauche/droite. Numéro de l’élément comme s’il se trouvait dans un tableau. Par exemple, si l’entrée de chaîne est `"Fox,Turtle,Rabbit,Wolf"` avec un index de 3, la sortie est `"Rabbit"`. Si l’index est supérieur au nombre d’éléments délimités, [Aucune option de valeur](no-value-options.md) ne s’applique.

## Analyse de l’URL

À utiliser avec des champs contenant des URL. Si l’on prend l’exemple d’URL `https://example.com/store/index.html?cid=campaign#cart`, les options suivantes sont disponibles :

* **[!UICONTROL Obtenir le protocole]** : obtenez le protocole de l’URL. Par exemple : `"https://"`.
* **[!UICONTROL Obtenir l’hôte]** : obtenez l’hôte de l’URL. Par exemple : `"example.com"`.
* **[!UICONTROL Obtenir le chemin]** : obtenez le chemin de l’URL. Par exemple : `"store/index.html"`.
* **[!UICONTROL Obtenir la valeur de la chaîne de requête]** : obtenez la valeur à partir d’une seule chaîne de requête. Placez le paramètre de chaîne de requête de votre choix dans le champ **[!UICONTROL Clé de requête]**. Si l’URL ci-dessus est utilisée avec la clé de requête `"cid"`, la sortie est `"campaign"`.
* **[!UICONTROL Obtenir la valeur de hachage]** : obtenez la valeur de hachage de l’URL. Par exemple : `"cart"`.

Si l’entrée n’est pas une URL valide ou si le composant URL souhaité n’est pas présent, [Aucune option de valeur](no-value-options.md) ne s’applique.

## Supprimer

Supprimez l’espace blanc ou les caractères spéciaux de la chaîne.

* **[!UICONTROL Supprimer les espaces]** : si elle est activée, cette case à cocher permet de supprimer tous les espaces au début et à la fin de la chaîne.
* **[!UICONTROL Supprimer les caractères spéciaux]** : si elle est activée, cette case à cocher affiche un champ d’entrée **[!UICONTROL Caractères spéciaux]**. Tous les caractères de ce champ sont supprimés de la sortie. Les caractères multioctets ne sont pas pris en charge.

## Regex

Appliquez des expressions régulières à une dimension pour récupérer la valeur souhaitée.

* **[!UICONTROL Regex]** : formule d’expression régulière.
* **[!UICONTROL Format de sortie]** : champ facultatif qui vous permet d’ajouter du texte ou de réorganiser la sortie du sous-groupe regex. Si ce champ est vide, la sortie de chaîne est l’expression régulière évaluée.
* **[!UICONTROL Respect de la casse]** : si elle est activée, cette case à cocher force l’expression régulière à être sensible à la casse.

CJA utilise un sous-ensemble de la syntaxe de l’expression régulière Perl. Si l’entrée ne correspond pas à l’expression régulière et que la variable **[!UICONTROL Format de sortie]** est vide, [Aucune option de valeur](no-value-options.md) ne s’applique. Les expressions ci-dessous sont prises en charge :

| Expression | Description |
| --- | --- |
| `a` | Un seul caractère `a`. |
| `a|b` | Un seul caractère `a` ou `b`. |
| `[abc]` | Un seul caractère `a`, `b` ou `c`. |
| `[^abc]` | N’importe quel caractère sauf `a`, `b` ou `c`. |
| `[a-z]` | N’importe quel caractère entre `a`-`z`. |
| `[a-zA-Z0-9]` | N’importe quel caractère entre `a`-`z`, `A`-`Z`, ou entre `0`-`9`. |
| `^` | Correspond au début de la ligne. |
| `$` | Correspond à la fin de la ligne. |
| `\A` | Début de chaîne. |
| `\z` | Fin de chaîne. |
| `.` | Correspond à n’importe quel caractère. |
| `\s` | N’importe quel espace. |
| `\S` | N’importe quel caractère sauf espace. |
| `\d` | N’importe quel chiffre. |
| `\D` | N’importe quel caractère non numérique. |
| `\w` | N’importe quel caractère de soulignement, lettre ou chiffre. |
| `\W` | N’importe quel caractère n’appartenant pas à un mot. |
| `\b` | N’importe quelle limite de mot. |
| `\B` | N’importe quel caractère qui n’est pas une limite de mot. |
| `\<` | Début de mot. |
| `\>` | Fin de mot. |
| `(...)` | Acquérir tout ce qui est compris. |
| `(?:...)` | Capture sans marquage. Empêche la référence de la correspondance dans la chaîne de sortie. |
| `a?` | Zéro ou un de : `a`. |
| `a*` | Zéro ou plus de : `a`. |
| `a+` | Un ou plus de : `a`. |
| `a{3}` | Exactement 3 de : `a`. |
| `a{3,}` | 3 ou plus de : `a`. |
| `a{3,6}` | Entre 3 et 6 de : `a`. |

Les espaces réservés de sortie sont également pris en charge. Vous pouvez utiliser ces séquences au **[!UICONTROL Format de sortie]** le nombre de fois désiré et dans n’importe quel ordre pour obtenir la sortie de chaîne souhaitée.

| Séquence d’espace réservé de sortie | Description |
| --- | --- |
| `$&` | Génère ce qui correspondait à l’expression entière. |
| `$n` | Génère ce qui correspondait à la énième sous-expression. Par exemple : `$1` génère la première sous-expression. |
| ``$` `` | Génère le texte entre la fin de la dernière correspondance trouvée (ou le début du texte si aucune correspondance précédente n’a été trouvée) et le début de la correspondance actuelle. |
| `$+` | Génère ce qui correspond à la dernière sous-expression marquée dans l’expression régulière. |
| `$$` | Génère le caractère de chaîne `"$"`. |

{style="table-layout:auto"}

## Vidéo sur les dimensions de liaison

Regardez cette vidéo sur les dimensions de liaison :

>[!VIDEO](https://video.tv.adobe.com/v/342694/?quality=12)
