---
title: Présentation de l’assemblage
description: Présentation de l’assemblage.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '1220'
ht-degree: 32%

---

# Présentation de l’assemblage

Le groupement d’identités (ou simplement le groupement) est une puissante fonctionnalité qui accroît la capacité d’un jeu de données d’événement à l’analyse cross-canal. L’analyse cross-canal est un cas d’utilisation principal que Customer Journey Analytics peut traiter, ce qui vous permet de combiner et d’exécuter en toute transparence des rapports sur plusieurs jeux de données de différents canaux, en fonction d’un identifiant commun (ID de personne).

Lorsque vous combinez des jeux de données avec des identifiants de personne similaires, l’attribution est transférée sur plusieurs appareils et canaux. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur rencontre un problème avec sa commande, puis appelle votre équipe du service client pour l’aider à résoudre ce problème. Avec l’analyse cross-canal, vous pouvez attribuer des événements du centre d’appel à la publicité sur laquelle ils ont cliqué à l’origine.

Malheureusement, tous les jeux de données basés sur un événement qui font partie de votre connexion en Customer Journey Analytics ne sont pas suffisamment renseignés avec des données pour prendre en charge cette attribution prête à l’emploi. En particulier, les jeux de données d’expérience web ou mobiles ne disposent souvent pas d’informations d’identification de personne réelles sur tous les événements.

L’assemblage permet de recomposer les identités dans les lignes d’un jeu de données, afin de s’assurer que l’identifiant de personne souhaité (ID assemblé) est disponible sur chaque événement. L’assemblage examine les données utilisateur des sessions authentifiées et non authentifiées pour générer un identifiant assemblé. L’assemblage permet de résoudre des enregistrements disparates sur un seul ID assemblé pour analyse au niveau de la personne, plutôt qu’au niveau de l’appareil ou du cookie.

Vous bénéficiez d’une analyse cross-canal si vous combinez un ou plusieurs de vos jeux de données assemblés à d’autres jeux de données, tels que les données du centre d’appels, dans le cadre de la définition de votre connexion de Customer Journey Analytics. Cela suppose que ces autres jeux de données contiennent déjà un ID de personne sur chaque ligne, similaire à l’ID associé.


## Conditions préalables

>[!IMPORTANT]
>
>Si vous ne remplissez pas toutes les conditions préalables, vous risquez de ne pas pouvoir effectuer correctement l’analyse cross-canal.

Avant d’utiliser le groupement, assurez-vous que votre organisation est préparée avec les éléments suivants :

* Importez les données de votre choix dans Adobe Experience Platform:

   * Pour les données Adobe Analytics, voir [Utilisation des données de suite de rapports Adobe Analytics dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * Pour d’autres types de données, consultez [Créer un schéma](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=fr) et [Ingérer des données](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=fr) dans la documentation d’Adobe Experience Platform.

* Le jeu de données dans Adobe Experience Platform auquel vous souhaitez appliquer la combinaison doit comporter deux colonnes qui permettent d’identifier les visiteurs :

   * Un **identifiant persistant**, un identifiant présent sur chaque ligne. Par exemple, un identifiant visiteur généré par une bibliothèque d’AppMeasurements Adobe Analytics ou un ECID généré par le service Adobe Experience Cloud Identity.
   * Un **identifiant transitoire**, identifiant présent sur certaines lignes seulement. Par exemple, un nom d’utilisateur ou une adresse e-mail chiffré une fois qu’un visiteur s’authentifie. Vous pouvez utiliser pratiquement n’importe quel identifiant, à condition qu’il soit présent au moins une fois sur le même événement qu’un identifiant persistant donné.

* L’assemblage comprend la fusion de données utilisateur authentifiées et non authentifiées. Veillez à respecter les lois et réglementations en vigueur, y compris l’obtention des autorisations nécessaires de l’utilisateur final, avant de fusionner des jeux de données.


## Utilisation de l’assemblage

Une fois que votre entreprise a satisfait à toutes les conditions préalables et a compris la variable [limitations](#limitations), vous pouvez suivre les étapes suivantes pour commencer à utiliser le groupement dans Customer Journey Analytics :

### Demande d’assistance

1. Contactez le service clientèle d’Adobe avec les informations suivantes :

   * Demande d’activation du groupement.
   * Identifiant du jeu de données pour le jeu dont vous souhaitez recomposer les données.
   * Nom de colonne de l’identifiant persistant du jeu de données souhaité (identifiant qui apparaît sur chaque ligne).
   * Nom de colonne de l’identifiant transitoire pour le jeu de données souhaité (lien d’identifiant de personne entre les jeux de données).
   * Votre préférence en matière de fréquence de [relecture](explained.md) et de durée de période de recherche arrière. Les options incluent une relecture une fois par semaine avec une période de recherche arrière de 7 jours ou une relecture chaque jour avec une période de recherche arrière de 1 jour.
   * Nom de la sandbox.


2. Le service clientèle d’Adobe travaille avec le service d’ingénierie d’Adobe pour activer l’assemblage à la réception de votre demande. Une fois lʼactivation effectuée, un nouveau jeu de données recréé contenant une nouvelle colonne ID de personne s’affiche dans Adobe Experience Platform. Le Service clientèle d’Adobe peut fournir le nouvel ID de jeu de données et le nom de colonne de l’ID de personne.

3. Lors de la première utilisation, Adobe fournit un renvoi de données assemblées qui remonte jusquʼau début du mois précédent (jusquʼà 60 jours). Pour effectuer ce renvoi, l’identifiant transitoire doit exister dans les données désassemblées à ce moment-là.

4. [Création d’une connexion](/help/connections/create-connection.md) dans Customer Journey Analytics à l’aide du nouveau jeu de données généré et de tous les autres jeux de données que vous souhaitez inclure. Choisissez l’identifiant de personne approprié pour chaque jeu de données.

5. [Créez une vue de données](/help/data-views/create-dataview.md) basée sur la connexion.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Une fois la vue de données configurée, l’analyse cross-canal en Customer Journey Analytics est identique à toute autre analyse en Customer Journey Analytics, sauf que les données fonctionnent désormais sur plusieurs canaux et périphériques.

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
>Appliquez également toute modification que vous apportez au schéma de jeu de données d’événement global au nouveau schéma de jeu de données assemblé, sinon il rompt le jeu de données assemblé.
>
>En outre, si vous supprimez le jeu de données source, le jeu de données assemblé cesse le traitement et est supprimé par le système.

L’assemblage est une fonctionnalité innovante et robuste, mais son utilisation est limitée.

* Les capacités de recomposition de données actuelles sont limitées à une étape (identifiant persistant à identifiant transitoire). La recomposition de données à plusieurs étapes (par exemple, un identifiant persistant à un identifiant transitoire, puis à un autre identifiant transitoire) n’est pas prise en charge.
* Seuls les jeux de données dʼévénement sont pris en charge. D’autres jeux de données, tels que les jeux de données de recherche, ne sont pas pris en charge.
* Les mappages d’identifiants personnalisés utilisés dans votre organisation ne sont pas pris en charge.
* L’assemblage ne transforme pas le champ utilisé pour le groupement d’aucune manière. L’assemblage utilise la valeur du champ spécifié telle qu’elle existe dans le jeu de données désassemblé dans le lac de données. Le processus dʼassemblage est sensible à la casse. Par exemple, si le mot &quot;Bob&quot; apparaît parfois dans le champ et que le mot &quot;BOB&quot; apparaît, ces ID sont traités comme deux personnes distinctes.
* L’assemblage est sensible à la casse. Pour les jeux de données générés par le biais d’Analytics Source Connector, Adobe recommande de consulter les règles VISTA ou de traitement qui s’appliquent au champ d’identifiant transitoire. Cette révision permet de s’assurer qu’aucune de ces règles n’introduit de nouvelles formes du même ID. Par exemple, vous devez vous assurer quʼaucune règle VISTA ou de traitement nʼintroduit de minuscules dans le champ ID temporaire sur une partie seulement des événements.
* L’assemblage ne combine ni ne concatène des champs.
* Le champ d’identifiant transitoire doit contenir un seul type d’identifiant (identifiants provenant d’un seul espace de noms). Par exemple, le champ ID temporaire ne doit pas contenir une combinaison dʼidentifiants de connexion et dʼadresses électroniques.
* Si plusieurs événements se produisent avec le même horodatage pour le même ID persistant, mais avec des valeurs différentes dans le champ ID transitoire, l’assemblage sélectionne l’ID en fonction de l’ordre alphabétique. Ainsi, si l’ID persistant A comporte deux événements avec le même horodatage et que l’un d’eux spécifie Bob et que l’autre spécifie Ann, l’assemblage sélectionne Ann.
* Si un appareil est partagé par plusieurs personnes et que le nombre total de transitions entre les utilisateurs dépasse 50 000, Customer Journey Analytics cesse de regrouper les données pour cet appareil.

Ne confondez pas l’assemblage avec :

* La fusion de plusieurs jeux de données. L’assemblage s’applique à un seul jeu de données. La fusion des jeux de données se produit suite à la configuration d’une connexion de Customer Journey Analytics et à la sélection du même ID de personne sur les jeux de données sélectionnés dans la connexion.

* La jointure de deux jeux de données. Dans Customer Journey Analytics, une jointure est souvent utilisée pour les recherches ou les classifications dans Analysis Workspace. Bien que l’assemblage utilise la fonctionnalité de jointure, le processus lui-même implique bien plus que des jointures.
