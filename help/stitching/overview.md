---
title: Présentation de l’assemblage
description: Vue d’ensemble du groupement
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 15%

---

# Présentation de l’assemblage

>[!NOTE]
>
>Pour utiliser la fonctionnalité décrite dans cette section, vous devez disposer du package **Select** ou supérieur (pour [ field-based stitching](fbs.md)) ou du package **Prime** ou supérieur (pour [graph-based stitching](gbs.md)). Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.

Le groupement d’identités (ou simplement le groupement) est une puissante fonctionnalité qui accroît la capacité d’un jeu de données d’événement à l’analyse cross-canal. L’analyse cross-canal est un cas d’utilisation principal que Customer Journey Analytics peut traiter, ce qui vous permet de combiner et d’exécuter des rapports de manière transparente sur plusieurs jeux de données de différents canaux, en fonction d’un identifiant commun (ID de personne).

Lorsque vous combinez des jeux de données avec des identifiants de personne similaires, l’attribution est transférée sur plusieurs appareils et canaux. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur rencontre un problème avec sa commande, puis appelle votre équipe du service client pour l’aider à résoudre ce problème. Avec l’analyse cross-canal, vous pouvez attribuer des événements du centre d’appel à la publicité sur laquelle ils ont cliqué à l’origine.

Malheureusement, tous les jeux de données basés sur un événement qui font partie de votre connexion en Customer Journey Analytics ne sont pas suffisamment renseignés avec des données pour prendre en charge cette attribution prête à l’emploi. En particulier, les jeux de données d’expérience web ou mobiles ne disposent souvent pas d’informations d’identification de personne réelles sur tous les événements.

L’assemblage permet de recomposer les identités dans les lignes d’un jeu de données, en s’assurant que l’ID de personne (ID assemblé) est disponible sur chaque événement. L’assemblage examine les données utilisateur des sessions authentifiées et non authentifiées afin de déterminer la valeur d’ID transitoire commun (ID de personne) qui peut être utilisée comme ID assemblé. Cette recomposition permet de résoudre des enregistrements disparates sur un seul identifiant assemblé à analyser au niveau de la personne, plutôt qu’au niveau de l’appareil ou du cookie.

Customer Journey Analytics prend en charge deux types de groupement : [groupement basé sur les champs](fbs.md) et [groupement basé sur les graphiques](gbs.md).

## Conditions préalables

>[!IMPORTANT]
>
>Si vous ne remplissez pas toutes les conditions préalables, vous risquez de ne pas pouvoir effectuer correctement l’analyse cross-canal.

Avant d’utiliser le groupement, assurez-vous que votre organisation est préparée avec les éléments suivants :

- L’assemblage comprend la fusion de données utilisateur authentifiées et non authentifiées. Veillez à respecter les lois et réglementations en vigueur, y compris l’obtention des autorisations nécessaires de l’utilisateur final, avant d’activer le groupement sur un jeu de données d’événement. Voir [Définir des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations.

- Importez les données souhaitées dans Adobe Experience Platform :

   - Pour les données Adobe Analytics, voir [Utilisation des données de suite de rapports Adobe Analytics dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Pour d’autres types de données, consultez [Créer un schéma](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) et [Ingérer des données](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) dans la documentation d’Adobe Experience Platform.

Vous bénéficiez d’une analyse cross-canal si vous combinez un ou plusieurs de vos jeux de données assemblés à d’autres jeux de données, tels que les données du centre d’appels, dans le cadre de la définition de votre connexion de Customer Journey Analytics. Cette configuration de connexion suppose que ces autres jeux de données contiennent déjà un ID de personne sur chaque ligne, similaire à l’ID associé.


## Limites

>[!IMPORTANT]
>
>- L’utilisation de `identityMap` comme identifiant persistant n’est pas prise en charge. Vous devez définir un identifiant spécifique dans le jeu de données (par exemple, `ECID`) comme identifiant persistant.
>
>- Appliquez également toute modification que vous apportez au schéma du jeu de données d’événement source au nouveau schéma du jeu de données assemblé, sinon il rompt le jeu de données assemblé.
>
>- Si vous supprimez le jeu de données source, le jeu de données assemblé cesse le traitement et est supprimé par le système.
>
>- Les libellés d’utilisation des données ne sont pas propagés automatiquement au schéma de jeu de données assemblé. Si des libellés d’utilisation des données sont appliqués au schéma du jeu de données source, vous devez appliquer ces libellés manuellement au schéma du jeu de données assemblé. Pour plus d’informations, voir [Gestion des libellés d’utilisation des données dans Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) .

L’assemblage est une fonctionnalité innovante et robuste, mais son utilisation est limitée.

- Seuls les jeux de données dʼévénement sont pris en charge. D’autres jeux de données, tels que les jeux de données de recherche, ne sont pas pris en charge.
- L’assemblage ne transforme pas le champ utilisé pour le groupement d’aucune manière. L’assemblage utilise la valeur du champ spécifié telle qu’elle existe dans le jeu de données désassemblé dans le lac de données.
- Le processus dʼassemblage est sensible à la casse. Par exemple, si le mot &quot;Bob&quot; apparaît parfois dans le champ et que le mot &quot;BOB&quot; apparaît, ces ID sont traités comme deux personnes distinctes.

Assurez-vous de ne pas confondre le groupement avec :

- La fusion de plusieurs jeux de données. L’assemblage s’applique à un seul jeu de données. La fusion des jeux de données se produit suite à la configuration d’une connexion de Customer Journey Analytics et à la sélection du même ID de personne dans les jeux de données sélectionnés de la connexion.

- La jointure de deux jeux de données. Dans Customer Journey Analytics, une jointure est souvent utilisée pour les recherches ou les classifications dans Analysis Workspace. Bien que l’assemblage utilise la fonctionnalité de jointure, le processus lui-même implique plus que des jointures.

>[!MORELIKETHIS]
>
>[Groupement basé sur les champs](fbs.md)
>[Groupement basé sur les graphiques](gbs.md)
>[Utilisation de l’assemblage](use-stitching.md)
>[Questions fréquentes sur l’assemblage](faq.md)

