---
title: Vue d’ensemble du groupement
description: Découvrez les concepts, les avantages, les conditions préalables et les limites de la combinaison d’identités.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 71%

---

# Vue d’ensemble du groupement

>[!NOTE]
>
>Vous devez disposer du package Customer Journey Analytics **Select** ou d’une version ultérieure (pour le [groupement basé sur les champs](fbs.md)) ou du package **Prime** Customer Journey Analytics ou d’une version ultérieure (pour le [groupement basé sur les graphiques](gbs.md)) pour utiliser la fonctionnalité décrite dans cette section. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.

Le groupement d’identités (ou groupement) est une puissante fonctionnalité qui élève la capacité d’un jeu de données d’événement à l’analyse cross-canal. L’analyse cross-canal est un cas d’utilisation principal pour Customer Journey Analytics. L’analyse cross-canal vous permet de combiner et d’exécuter facilement des rapports sur plusieurs jeux de données de différents canaux, en fonction d’un identifiant commun (ID de personne).

Lorsque vous combinez des jeux de données avec des identifiants de personne similaires, l’attribution est transférée sur plusieurs appareils et canaux. Par exemple, un utilisateur ou une utilisatrice consulte votre site par le biais d’une publicité reçue sur son poste de travail. L’utilisateur achète un produit, mais il rencontre ensuite un problème avec la commande. Elle appelle ensuite votre équipe du service clientèle pour l’aider à résoudre le problème. Avec l’analyse cross-canal, vous pouvez attribuer des événements de centre d’appel à l’annonce publicitaire qui a fait l’objet d’un clic à l’origine.

Malheureusement, tous les jeux de données basés sur un événement qui font partie de votre connexion dans Customer Journey Analytics ne sont pas suffisamment alimentées en données pour prendre en charge cette attribution dès le départ. En particulier, les jeux de données d’expérience web ou mobiles ne disposent souvent pas d’informations d’ID de personne pour tous les événements.

L’assemblage des clés d’identité dans les lignes d’un jeu de données pour s’assurer que l’ID de personne (ID assemblé) est disponible sur chaque événement. Le rapprochement examine les données utilisateur des sessions authentifiées et non authentifiées afin de déterminer la valeur de l’ID de personne commun qui peut être utilisée en tant qu’ID rapproché. Cette recomposition résout les enregistrements disparates en un seul identifiant assemblé pour une analyse au niveau de la personne, plutôt qu’au niveau de l’appareil ou du cookie.

Customer Journey Analytics prend en charge deux types de groupement : le [groupement basé sur les champs](fbs.md) et le [groupement basé sur les graphes](gbs.md).

## Conditions préalables

>[!IMPORTANT]
>
>Si toutes les conditions préalables ne sont pas remplies, il peut être impossible de réaliser correctement une analyse cross-canal.

Avant d’utiliser le groupement, veillez à ce que votre organisation dispose des éléments suivants :

- Le groupement inclut la fusion des données d’utilisateur et d’utilisatrice authentifiées et non authentifiées. Veillez à respecter les lois et réglementations applicables, y compris l’obtention des autorisations nécessaires de l’utilisateur final, avant d’activer le groupement sur un jeu de données d’événement.

- Importez les données de votre choix dans Adobe Experience Platform :

   - Pour les données Adobe Analytics, consultez [Utiliser les données de suite de rapports Adobe Analytics dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Pour d’autres types de données, consultez [Créer un schéma](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/tutorials/create-schema-ui) et [Ingérer des données](https://experienceleague.adobe.com/fr/docs/experience-platform/ingestion/home) dans la documentation d’Adobe Experience Platform.

L’analyse cross-canal vous est utile si vous combinez un ou plusieurs des jeux de données groupés avec d’autres jeux de données, tels que les données de centre d’appel, dans le cadre de la définition de votre connexion Customer Journey Analytics. Cette configuration de connexion suppose que ces autres jeux de données contiennent déjà un ID de personne sur chaque ligne, similaire à l’ID groupé.

## Activer le rapprochement

Vous pouvez activer le rapprochement de deux manières différentes :

- [Demande d’activation du groupement](/help/stitching/use-stitching.md) (obsolète). Une fois approuvé, un jeu de données en double est créé pour le jeu de données pour lequel vous avez demandé un groupement. Ce jeu de données en double contient une colonne supplémentaire avec l’identifiant assemblé. Vous devez créer une connexion ou en modifier une existante qui inclut le jeu de données assemblé pour utiliser les données assemblées dans Customer Journey Analytics.
- [Activer l’assemblage dans l’interface Connexions](/help/stitching/use-stitching-ui.md). Lorsque vous configurez le groupement pour un jeu de données dans l’interface Connexions, le groupement se produit à la volée, lors de l’ingestion des données de ce jeu de données dans Customer Journey Analytics.

## Limites

L’analyse cross-canal est une fonctionnalité innovante et robuste, mais son utilisation a ses limites.

- Seuls les jeux de données dʼévénement sont pris en charge. D’autres jeux de données, tels que les jeux de données de recherche, ne sont pas pris en charge.
- Lʼanalyse cross-canal ne transforme pas le champ utilisé pour le groupement de quelque manière que ce soit. Le groupement basé sur les champs utilise la valeur du champ spécifié telle quʼelle existe dans le jeu de données non groupé au sein du lac de données.
- Le processus de groupement respecte la casse. Par exemple, les valeurs d’identité `Bob` et `BOB` sont traitées comme deux personnes distinctes.

Veillez à ne pas confondre le groupement avec ce qui suit :

- Fusion de plusieurs jeux de données. Le groupement s’applique à un seul jeu de données. La fusion des jeux de données se produit suite à la configuration d’une connexion Customer Journey Analytics et à la sélection du même ID de personne dans les jeux de données sélectionnés dans la connexion.

- Jointure de deux jeux de données. Dans Customer Journey Analytics, une jointure est souvent utilisée pour les recherches ou les classifications dans Analysis Workspace. Bien que le groupement utilise la fonctionnalité de jointure, le processus lui-même implique plus de jointures.


## Jeux de données Journey Optimizer

L’assemblage prend en charge les jeux de données Journey Optimizer suivants, générés automatiquement :

- Événements d’étape de parcours AJO
- Jeu de données d’événement d’activité entrante AJO
- Jeu de données de surfaces AJO
- Jeu de données d’événement de commentaires de message AJO* Jeu de données d’événement d’expérience de suivi des notifications push AJO
- Jeu de données d’événement d’expérience de suivi d’e-mail AJO
- Jeu de données d’événement de commentaires en Cci AJO
- Jeu de données d’événement de commentaires des activités en direct AJO
- Jeu de données d’événement de décision ExD AJO

>[!MORELIKETHIS]
>
>[Rapprochement basé sur les champs](fbs.md)
>[Rapprochement basé sur les graphiques](gbs.md)
>[Utiliser le groupement](use-stitching.md)
>[Valider le groupement](validate.md)
>[Questions fréquentes sur le groupement](faq.md)

