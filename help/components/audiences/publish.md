---
title: Création et publication d’audiences dans Real-time Customer Profile
description: Découvrez comment publier des audiences à partir de Customer Journey Analytics
source-git-commit: 7895342fb33118f0bbe97ce4a7adc22664adf000
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 10%

---


# Création et publication d’audiences

Cette rubrique explique comment publier les audiences découvertes dans Customer Journey Analytics (CJA) sur [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr) dans Adobe Experience Platform pour le ciblage et la personnalisation des clients.

## Créer une audience

1. Pour créer des audiences, vous avez trois façons de commencer :

   | Méthode de création | Détails |
   | --- | --- |
   | De **[!UICONTROL Composants] > [!UICONTROL Audiences]** | La page Audiences Manager s’ouvre. Cliquez sur **[!UICONTROL Créer une audience]** et le [!UICONTROL Audience Builder] s’ouvre. |
   | Dans un tableau à structure libre | Cliquez avec le bouton droit de la souris sur un élément d’un tableau à structure libre, puis sélectionnez **[!UICONTROL Création d’une audience d’après une sélection]**. L’utilisation de cette méthode préremplit le filtre avec la dimension ou l’élément de dimension que vous avez sélectionné dans le tableau. |
   | Depuis l’interface utilisateur de modification des filtres | Cochez la case qui indique : **[!UICONTROL Créer une audience à partir de ce filtre]**. L’utilisation de cette méthode préremplit le filtre. |

   {style=&quot;table-layout:auto&quot;}

1. Configurez l’audience.

   | Paramètre | Description |
   | --- | --- |
   | [!UICONTROL Nom] | Nom de l’audience. |
   | [!UICONTROL Balises] | Toutes les balises que vous souhaitez attribuer à l’audience à des fins d’organisation. Vous pouvez utiliser une balise préexistante ou en saisir une nouvelle. |
   | [!UICONTROL Description] | Ajoutez une bonne description de l’audience pour la différencier des autres. |
   | [!UICONTROL Fréquence d’actualisation] | Fréquence à laquelle vous souhaitez actualiser l’audience.<ul><li>Vous pouvez choisir de créer une audience unique (par défaut) qui ne nécessite aucune actualisation, ce qui peut s’avérer utile pour des campagnes ponctuelles spécifiques, par exemple.</li><li>Vous pouvez sélectionner d’autres intervalles d’actualisation. Pour la fréquence de 4 heures, il existe une limite de 150 audiences, car ce taux d’actualisation est très intensif en traitement. Pour les autres intervalles, il n’y a pas de nombre maximal d’audiences.</li></ul> |
   | Date d’expiration | Lorsque l’audience cessera de s’actualiser. La valeur par défaut est d’un an à compter de la date de création. |
   | Actualiser l’intervalle de recherche en amont | Indique le chemin à parcourir dans la fenêtre de données lors de la création de cette audience. max. est de 90 jours. Les audiences arrivant à expiration sont traitées de la même manière que les rapports planifiés arrivant à expiration : l’administrateur reçoit un courrier électronique un mois avant l’expiration du planning. |
   | [!UICONTROL Période ponctuelle] | Période à laquelle vous souhaitez que l’audience unique soit publiée. |
   | [!UICONTROL Filtrer] | Les filtres sont la principale entrée de l’audience. Vous pouvez ajouter jusqu’à 20 filtres. Ces filtres peuvent être joints par `And` ou `Or` opérateurs. |

   {style=&quot;table-layout:auto&quot;}

1. Interpréter l’aperçu des données.

   L’aperçu de l’audience s’affiche dans le rail de droite.

   | Paramètre d’aperçu | Description |
   | --- | --- |
   | Fenêtre d&#39;aperçu des données | La période de l’audience. |
   | Nombre total de personnes dans l’audience | Un nombre qui peut atteindre 100 millions. |
   | Limite de taille d’audience | Indique à quel point cette audience est éloignée de la limite de 100 millions de milliards. |
   | Retour dʼaudience estimé |  |
   | Retour estimé | Un numéro de résumé... |
   | Prévisualiser les mesures |  |

   {style=&quot;table-layout:auto&quot;}


