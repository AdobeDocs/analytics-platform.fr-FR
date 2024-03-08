---
title: Présentation de l’assemblage
description: Présentation du groupement.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 18%

---

# Présentation de l’assemblage

Le groupement d’identités (ou simplement le groupement) est une puissante fonctionnalité qui accroît la capacité d’un jeu de données d’événement à l’analyse cross-canal. L’analyse cross-canal est un cas d’utilisation principal que Customer Journey Analytics peut traiter, ce qui vous permet de combiner et d’exécuter en toute transparence des rapports sur plusieurs jeux de données de différents canaux, en fonction d’un identifiant commun (ID de personne).

Lorsque vous combinez des jeux de données avec des identifiants de personne similaires, l’attribution est transférée sur plusieurs appareils et canaux. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur rencontre un problème avec sa commande, puis appelle votre équipe du service client pour l’aider à résoudre ce problème. Avec l’analyse cross-canal, vous pouvez attribuer des événements du centre d’appel à la publicité sur laquelle ils ont cliqué à l’origine.

Malheureusement, tous les jeux de données basés sur un événement qui font partie de votre connexion en Customer Journey Analytics ne sont pas suffisamment renseignés avec des données pour prendre en charge cette attribution prête à l’emploi. En particulier, les jeux de données d’expérience web ou mobiles ne disposent souvent pas d’informations d’identification de personne réelles sur tous les événements.

L’assemblage permet de recomposer les identités dans les lignes d’un jeu de données, en s’assurant que l’ID de personne (ID assemblé) est disponible sur chaque événement. L’assemblage examine les données utilisateur des sessions authentifiées et non authentifiées afin de déterminer la valeur d’identifiant transitoire courante qui peut être utilisée comme identifiant assemblé. Cette recomposition permet de résoudre des enregistrements disparates sur un seul identifiant assemblé à analyser au niveau de la personne, plutôt qu’au niveau de l’appareil ou du cookie.

Vous bénéficiez d’une analyse cross-canal si vous combinez un ou plusieurs de vos jeux de données assemblés à d’autres jeux de données, tels que les données du centre d’appels, dans le cadre de la définition de votre connexion de Customer Journey Analytics. Cela suppose que ces autres jeux de données contiennent déjà un ID de personne sur chaque ligne, similaire à l’ID associé.


## Conditions préalables

{{select-package}}

>[!IMPORTANT]
>
>Si vous ne remplissez pas toutes les conditions préalables, vous risquez de ne pas pouvoir effectuer correctement l’analyse cross-canal.

Avant d’utiliser le groupement, assurez-vous que votre organisation est préparée avec les éléments suivants :

* Importez les données souhaitées dans Adobe Experience Platform :

   * Pour les données Adobe Analytics, voir [Utilisation des données de suite de rapports Adobe Analytics dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * Pour d’autres types de données, consultez [Créer un schéma](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=fr) et [Ingérer des données](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=fr) dans la documentation d’Adobe Experience Platform.

* Le jeu de données d’événement dans Adobe Experience Platform auquel vous souhaitez appliquer la combinaison doit comporter deux colonnes qui permettent d’identifier les visiteurs :

   * Un **identifiant persistant**, un identifiant présent sur chaque ligne. Par exemple, un identifiant visiteur généré par une bibliothèque d’AppMeasurements Adobe Analytics ou un ECID généré par le service Adobe Experience Cloud Identity.
   * Un **identifiant transitoire**, identifiant présent sur certaines lignes seulement. Par exemple, un nom d’utilisateur ou une adresse e-mail chiffré une fois qu’un visiteur s’authentifie. Vous pouvez utiliser pratiquement n’importe quel identifiant. L’assemblage considère ce champ comme contenir les informations d’identification de la personne. Pour de meilleurs résultats de regroupement, un identifiant transitoire doit être envoyé dans les événements du jeu de données au moins une fois pour chaque identifiant persistant. Si vous prévoyez d’inclure ce jeu de données dans une connexion de Customer Journey Analytics, il est préférable que les autres jeux de données aient également un identifiant commun similaire.

  Les deux colonnes (identifiant persistant et identifiant transitoire) doivent être définies comme un champ d’identité avec un espace de noms d’identité dans le schéma sous-jacent au jeu de données que vous souhaitez assembler. Lors de l’utilisation de la combinaison d’identités dans Real-time Customer Data Platform à l’aide de la variable [groupe de champs identityMap](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#identity), vous devez toujours ajouter des champs d’identité avec un espace de noms d’identité, car le regroupement de Customer Journey Analytics décrit dans cette section ne prend pas en charge le groupe de champs identityMap . Lors de l’ajout d’un champ d’identité dans le schéma tout en utilisant le groupe de champs identityMap , ne définissez pas le champ d’identité supplémentaire comme identité principale, car cela interférera avec le groupe de champs identityMap utilisé pour Real-time Customer Data Platform.

* L’assemblage comprend la fusion de données utilisateur authentifiées et non authentifiées. Veillez à respecter les lois et réglementations en vigueur, y compris l’obtention des autorisations nécessaires de l’utilisateur final, avant d’activer le groupement sur un jeu de données d’événement. Voir [Définition des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#) pour plus d’informations.


## Utilisation de l’assemblage

Une fois que votre entreprise a satisfait à toutes les conditions préalables et a compris la variable [limitations](#limitations), vous pouvez suivre les étapes suivantes pour commencer à utiliser le groupement dans Customer Journey Analytics :

### Demande d’assistance

1. Contactez le service clientèle d’Adobe avec les informations suivantes :

   * Demande d’activation du groupement.
   * Identifiant du jeu de données pour le jeu de données que vous souhaitez recomposer.
   * Nom de colonne de l’identifiant persistant du jeu de données souhaité (identifiant qui apparaît sur chaque ligne).
   * Nom de colonne de l’identifiant transitoire pour le jeu de données souhaité (l’identifiant de personne, qui agit également comme lien entre les jeux de données dans le contexte d’une connexion).
   * Votre préférence en matière de fréquence de [relecture](explained.md) et de durée de période de recherche arrière. Les options incluent une relecture une fois par semaine avec une période de recherche arrière de 7 jours ou une relecture chaque jour avec une période de recherche arrière de 1 jour.
   * Nom de la sandbox.


2. Le service clientèle d’Adobe travaille avec le service d’ingénierie d’Adobe pour activer l’assemblage à la réception de votre demande. Une fois activé, un nouveau jeu de données recomposées contenant une nouvelle colonne Identifiant regroupé apparaît dans Adobe Experience Platform. Le service clientèle d’Adobe peut fournir l’identifiant du nouveau jeu de données.

3. Lorsqu’il est activé pour la première fois, Adobe fournit un renvoi de données assemblées qui remonte à 60 jours.

4. Si vous souhaitez utiliser le nouveau jeu de données assemblé dans une analyse cross-canal, vous devez l’ajouter à un [connection](../connections/overview.md) en Customer Journey Analytics avec tous les autres jeux de données nécessaires. Choisissez l’identifiant de personne approprié pour chaque jeu de données.

5. [Créez une vue de données](/help/data-views/create-dataview.md) basée sur la connexion.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Une fois la vue de données configurée, vous pouvez exécuter l’analyse des rapports du Customer Journey Analytics sur les canaux et les appareils.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## Limites

>[!IMPORTANT]
>
>* Appliquez également toute modification apportée au schéma de jeu de données d’événement global au nouveau schéma de jeu de données assemblé, sinon il rompt le jeu de données assemblé.
>
>* Si vous supprimez le jeu de données source, le jeu de données assemblé cesse le traitement et est supprimé par le système.
>
>* Les libellés d’utilisation des données ne sont pas propagés automatiquement au schéma de jeu de données assemblé. Si des libellés d’utilisation des données sont appliqués au schéma du jeu de données source, vous devez appliquer manuellement ces libellés à ce schéma du jeu de données assemblé. Voir [Gestion des libellés d’utilisation des données dans Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=fr) pour plus d’informations.

L’assemblage est une fonctionnalité innovante et robuste, mais son utilisation est limitée.

* Les capacités de recomposition de données actuelles sont limitées à une étape (identifiant persistant à identifiant transitoire). La recomposition de données à plusieurs étapes (par exemple, un identifiant persistant à un identifiant transitoire, puis à un autre identifiant transitoire) n’est pas prise en charge.
* Seuls les jeux de données dʼévénement sont pris en charge. D’autres jeux de données, tels que les jeux de données de recherche, ne sont pas pris en charge.
* Les mappages d’identifiants personnalisés utilisés dans votre organisation ne sont pas pris en charge.
* L’assemblage ne transforme pas le champ utilisé pour le groupement d’aucune manière. L’assemblage utilise la valeur du champ spécifié telle qu’elle existe dans le jeu de données désassemblé dans le lac de données. Le processus dʼassemblage est sensible à la casse. Par exemple, si le mot &quot;Bob&quot; apparaît parfois dans le champ et que le mot &quot;BOB&quot; apparaît, ces ID sont traités comme deux personnes distinctes.
* L’assemblage est sensible à la casse. Pour les jeux de données générés par le biais du connecteur source Analytics, Adobe recommande de vérifier les règles VISTA ou les règles de traitement qui s’appliquent au champ d’identifiant transitoire. Cette révision permet de s’assurer qu’aucune de ces règles n’introduit de nouvelles formes du même ID. Par exemple, vous devez vous assurer quʼaucune règle VISTA ou de traitement nʼintroduit de minuscules dans le champ ID temporaire sur une partie seulement des événements.
* L’assemblage ne combine ni ne concatène des champs.
* Le champ d’identifiant transitoire doit contenir un seul type d’identifiant (identifiants provenant d’un seul espace de noms). Par exemple, le champ ID temporaire ne doit pas contenir une combinaison dʼidentifiants de connexion et dʼadresses électroniques.
* Si plusieurs événements se produisent avec le même horodatage pour le même ID persistant, mais avec des valeurs différentes dans le champ ID transitoire, l’assemblage sélectionne l’ID en fonction de l’ordre alphabétique. Ainsi, si l’ID persistant A comporte deux événements avec le même horodatage et que l’un d’eux spécifie Bob et que l’autre spécifie Ann, l’assemblage sélectionne Ann.
* Si un appareil est partagé par plusieurs personnes et que le nombre total de transitions entre les utilisateurs dépasse 50 000, Customer Journey Analytics cesse de regrouper les données pour cet appareil.
* Soyez prudent lorsque les identifiants transitoires contiennent des valeurs d’espace réservé, par exemple &quot;Non défini&quot;. Voir [FAQ](faq.md) pour plus d’informations.

Ne confondez pas l’assemblage avec :

* La fusion de plusieurs jeux de données. L’assemblage s’applique à un seul jeu de données. La fusion des jeux de données se produit suite à la configuration d’une connexion de Customer Journey Analytics et à la sélection du même ID de personne sur les jeux de données sélectionnés dans la connexion.

* La jointure de deux jeux de données. Dans Customer Journey Analytics, une jointure est souvent utilisée pour les recherches ou les classifications dans Analysis Workspace. Bien que l’assemblage utilise la fonctionnalité de jointure, le processus lui-même implique plus que des jointures.
