---
title: Présentation du groupement
description: Vue d’ensemble du groupement
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 1a697ce0372d1cb544940778850714a198a000ec
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 15%

---

# Présentation du groupement

>[!NOTE]
>
>Vous devez disposer du package **Select** ou d’un package supérieur (pour le [groupement basé sur les champs](fbs.md)) ou du package **Prime** ou d’un package supérieur (pour le [groupement basé sur les graphiques](gbs.md)) pour utiliser la fonctionnalité décrite dans cette section. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.

L’assemblage des identités (ou simplement l’assemblage) est une fonctionnalité puissante qui améliore l’adaptabilité d’un jeu de données d’événement à l’analyse cross-canal. L’analyse cross-canal est un cas d’utilisation principal que Customer Journey Analytics peut gérer. Elle vous permet de combiner et d’exécuter des rapports en toute transparence sur plusieurs jeux de données provenant de différents canaux, en fonction d’un identifiant commun (ID de personne).

Lorsque vous combinez des jeux de données avec des identifiants de personne similaires, l’attribution est transférée sur plusieurs appareils et canaux. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur rencontre un problème avec sa commande, puis appelle votre équipe du service client pour l’aider à résoudre ce problème. Avec l’analyse cross-canal, vous pouvez attribuer des événements du centre d’appel à la publicité sur laquelle ils ont cliqué à l’origine.

Malheureusement, tous les jeux de données basés sur un événement qui font partie de votre connexion dans Customer Journey Analytics ne sont pas suffisamment renseignés avec des données pour prendre en charge cette attribution prête à l’emploi. En particulier, les jeux de données d’expérience web ou mobiles ne disposent souvent pas d’informations d’ID de personne réelles disponibles pour tous les événements.

L’assemblage permet de recomposer les identités dans les lignes d’un jeu de données, en s’assurant que l’ID de personne (ID assemblé) est disponible sur chaque événement. L’assemblage examine les données utilisateur des sessions authentifiées et non authentifiées afin de déterminer la valeur de l’ID transitoire commun (ID de personne) qui peut être utilisée comme ID assemblé. Cette recomposition permet de résoudre des enregistrements disparates en un seul identifiant assemblé pour une analyse au niveau de la personne, plutôt qu’au niveau de l’appareil ou du cookie.

Customer Journey Analytics prend en charge deux types de groupement : le [groupement basé sur les champs](fbs.md) et le [groupement basé sur les graphiques](gbs.md).

## Conditions préalables

>[!IMPORTANT]
>
>Si toutes les conditions préalables ne sont pas remplies, il peut être impossible de réaliser correctement une analyse cross-canal.

Avant d’utiliser le groupement, veillez à ce que votre organisation dispose des éléments suivants :

- L’assemblage inclut la fusion des données utilisateur authentifiées et non authentifiées. Veillez à respecter les lois et réglementations applicables, y compris l’obtention des autorisations nécessaires de l’utilisateur final, avant d’activer le groupement sur un jeu de données d’événement. Voir [Définir des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations.

- Importez les données de votre choix dans Adobe Experience Platform :

   - Pour les données Adobe Analytics, voir [Utilisation des données de suite de rapports Adobe Analytics dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Pour d’autres types de données, consultez [Créer un schéma](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) et [Ingérer des données](https://experienceleague.adobe.com/fr/docs/experience-platform/ingestion/home) dans la documentation d’Adobe Experience Platform.

L’analyse cross-canal vous est utile si vous combinez un ou plusieurs de vos jeux de données groupés avec d’autres jeux de données, tels que les données de centre d’appels, dans le cadre de la définition de votre connexion Customer Journey Analytics. Cette configuration de connexion suppose que ces autres jeux de données contiennent déjà un ID de personne sur chaque ligne, similaire à l’ID assemblé.


## Limites

>[!IMPORTANT]
>
>
>- Appliquez également toute modification que vous apportez au schéma du jeu de données d’événement source au nouveau schéma du jeu de données groupé, sinon le jeu de données groupé sera rompu.
>
>- Si vous supprimez le jeu de données source, le jeu de données assemblé cesse le traitement et est supprimé par le système.
>
>- Les libellés d’utilisation des données ne sont pas automatiquement propagés au schéma du jeu de données groupé. Si des libellés d’utilisation des données sont appliqués au schéma du jeu de données source, vous devez appliquer manuellement ces libellés d’utilisation des données au schéma du jeu de données assemblé. Consultez [ Gestion des libellés d’utilisation des données dans Experience Platform ](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) pour plus d’informations.

L’assemblage est une fonctionnalité innovante et robuste, mais son utilisation a ses limites.

- Seuls les jeux de données dʼévénement sont pris en charge. D’autres jeux de données, tels que les jeux de données de recherche, ne sont pas pris en charge.
- Le groupement ne transforme en rien le champ utilisé pour le groupement. L’assemblage utilise la valeur du champ spécifié telle qu’elle existe dans le jeu de données désassemblé du lac de données.
- Le processus dʼassemblage est sensible à la casse. Par exemple, si parfois le mot « Bob » apparaît dans le champ, et parfois le mot « BOB » apparaît, ces identifiants sont traités comme deux personnes distinctes.

Veillez à ne pas confondre le groupement avec :

- Fusion de plusieurs jeux de données. L’assemblage s’applique à un seul jeu de données. La fusion des jeux de données se produit suite à la configuration d’une connexion Customer Journey Analytics et à la sélection du même ID de personne dans les jeux de données sélectionnés dans la connexion.

- La jointure de deux jeux de données. Dans Customer Journey Analytics, une jointure est souvent utilisée pour les recherches ou les classifications dans Analysis Workspace. Bien que l’assemblage utilise la fonctionnalité de jointure, le processus lui-même implique plus de jointures.

>[!MORELIKETHIS]
>
>[Groupement basé sur les champs](fbs.md)
>[Assemblage basé sur les graphiques](gbs.md)
>[Utilisez le groupement](use-stitching.md)
>[Validez le groupement](validate.md)
>[Questions fréquentes sur le groupement ](faq.md)

