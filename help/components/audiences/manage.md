---
title: Gérer les audiences créées dans Customer Journey Analytics
description: Apprenez à gérer les audiences dans Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
source-git-commit: 86998458bd79f1fc17c17e58932b2b8434abf041
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 92%

---

# Gérer les audiences créées dans Customer Journey Analytics

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

La gestion des audiences créées précédemment permet de :

* **Planifier ou déplanifier** l’actualisation/mise à jour automatique de l’audience. L’expiration maximale du planning est d’un an.
* **Renouveler le planning d’actualisation d’une audience** sur le point d’expirer. Les audiences arrivant à expiration sont traitées de la même manière que les rapports planifiés arrivant à expiration : l’administrateur reçoit un e-mail un mois avant l’expiration du planning.
* Afficher la variable **intervalle d’actualisation** et le **dernière mise à jour d’une audience**
* Obtenez des informations sur **le temps nécessaire à la production d’une audience** de Customer Journey Analytics (CJA) et le temps nécessaire pour que l’audience apparaisse dans le profil client en temps réel à des fins d’activation.
* Vérifiez si les audiences dans CJA sont **utilisées de manière active par le profil client en temps réel** ou (idéalement) toute application Experience Platform qui consomme les audiences créées par CJA.

## Interface utilisateur de gestion

![](assets/manage.png)

| Paramètre de l’interface utilisateur | Définition |
| --- | --- |
| Masquer/afficher les filtres | Permet d’afficher ou de masquer les filtres suivants dans le rail de gauche : <ul><li>[!UICONTROL Vue de données]</li><li>[!UICONTROL Propriétaire]</li><li>[!UICONTROL Fréquence d’actualisation]</li><li>[!UICONTROL Balises]</li></ul> |
| [!UICONTROL Titre et description] | Titre et description donnés à l’audience lors de sa création. |
| [!UICONTROL Vue de données] | Vue de données dans laquelle cette audience a été créée. |
| [!UICONTROL Taille de l’audience] | Nombre total de personnes dans cette audience. |
| [!UICONTROL Propriétaire] | Propriétaire de l’audience : personne qui l’a créée. |
| [!UICONTROL Fréquence d’actualisation] | Intervalle d’actualisation qui a été configuré lors de la création de l’audience. |
| [!UICONTROL Balises] | Toutes les balises qui sont appliquées à cette audience. |
| [!UICONTROL Statut de publication] | Peut afficher [!UICONTROL Prêt], [!UICONTROL En cours]ou [!UICONTROL Erreur]. |
| [!UICONTROL  Dernière actualisation] | La dernière actualisation de l’audience. |
| [!UICONTROL Dernière modification] | Date de dernière modification de l’audience. |

{style=&quot;table-layout:auto&quot;}
