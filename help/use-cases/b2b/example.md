---
title: Exemple de projet B2B
description: Découvrez comment configurer et générer des rapports sur les données B2B
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 912e6a3200cdc8463667266f9cae75e4f6278337
workflow-type: tm+mt
source-wordcount: '1262'
ht-degree: 12%

---

# Exemple de projet B2B

Cet article illustre un cas pratique où vous souhaitez générer des rapports appropriés en Customer Journey Analytics sur les données de personne dans le contexte d’une configuration B2B standard. Une telle configuration fait partie du [B2B edition Real-Time CDP](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview).  Le cas d’utilisation explique comment configurer, configurer et générer des rapports au niveau du profil (personne) en fonction des données B2B dans Customer Journey Analytics.

## Connexion

Définissez votre connexion pour inclure tous les jeux de données B2B pertinents provenant d’Experience Platform. Jeux de données que vous pouvez envisager d’ajouter à votre connexion :

| Jeu de données | Schéma | Type de schéma | Classe de base | Description |
|---|---|---|---|---|
| Jeu de données d’activité B2B | Schéma d’activité B2B | Événement | XDM ExperienceEvent | Un ExperienceEvent est un enregistrement factuel de ce qui s’est produit, y compris le moment et l’identité de la personne impliquée. Les événements d’expérience peuvent être explicites (actions humaines directement observables) ou implicites (obtenus sans action humaine directe), et sont enregistrés sans agrégation ni interprétation. Les événements d’expérience sont essentiels à l’analyse du domaine temporel, car ils permettent l’observation et l’analyse des modifications qui se produisent dans une fenêtre de temps donnée, ainsi que la comparaison entre plusieurs fenêtres de temps pour suivre les tendances. |
| Jeu de données de personne B2B | Schéma de personne B2B | Profile | XDM Individual Profile | Un profil XDM individuel forme une représentation singulière des attributs et des intérêts des individus identifiés et partiellement identifiés. Les profils moins identifiés peuvent contenir uniquement des signaux comportementaux anonymes, tels que des cookies de navigateur, tandis que les profils hautement identifiés peuvent contenir des informations personnelles détaillées telles que le nom, la date de naissance, l’emplacement et l’adresse électronique. À mesure qu’un profil se développe, il devient un solide référentiel d’informations personnelles, d’informations d’identification, de coordonnées et de préférences de communication pour une personne. |
| Jeu de données de compte B2B | Schéma du compte B2B | Recherche | Compte d’entreprise XDM | Un compte XDM Business est une classe XDM standard qui capture les propriétés minimales requises d’un compte d’entreprise. Cette classe XDM ne peut être incluse dans le profil que pour les clients disposant de l’édition B2B ou B2P. |
| Jeu de données d’opportunité B2B | Schéma d’opportunité B2B | Recherche | XDM Business Opportunity | XDM Business Opportunity est une classe XDM standard qui capture les propriétés minimales requises d’une opportunité commerciale. Cette classe XDM ne peut être incluse dans le profil que pour les clients disposant de l’édition B2B ou B2P. |
| Jeu de données de campagne B2B | Schéma de campagne B2B | Recherche | XDM Business Campaign | XDM Business Campaign est une classe XDM (Experience Data Model) standard qui capture les propriétés minimales requises d’une campagne commerciale. Cette classe XDM ne peut être incluse dans le profil que pour les clients disposant de l’édition B2B ou B2P. |
| Jeu de données de liste marketing B2B | Schéma de liste marketing B2B | Recherche | Liste XDM Business Marketing | XDM Business Marketing List est une classe XDM standard qui capture les propriétés minimales requises d’une liste marketing. Les listes marketing vous permettent de classer par priorité les clients prospects les plus susceptibles d’acheter votre produit. Cette classe XDM ne peut être incluse dans le profil que pour les clients disposant de l’édition B2B ou B2P. |
| Jeu de données sur la relation de personne de compte B2B | Schéma de relation de personne de compte B2B | Recherche | Relation Personne/Compte d’entreprise XDM | XDM Business Account Person Relation est une classe XDM (modèle de données d’expérience) standard qui capture les propriétés minimales requises d’une personne associée à un compte d’entreprise. |
| Jeu de données de relation d’opportunité B2B | Schéma de relation de personne d’opportunité B2B | Recherche | Relation Personne/XDM Business Opportunity | XDM Business Opportunity Person Relation est une classe de modèle de données d’expérience (XDM) standard qui capture les propriétés minimales requises d’une personne associée à une opportunité commerciale. |
| Jeu de données des membres de liste marketing B2B | Schéma de membre de liste marketing B2B | Recherche | Membres de la liste marketing XDM | XDM Business Marketing List Members est une classe XDM standard qui décrit les membres, les personnes ou les contacts associés à une liste marketing. |
| Jeu de données des membres de campagne B2B | Schéma de membre de campagne B2B | Recherche | Membres de XDM Business Campaign | XDM Business Campaign Members est une classe de modèle de données d’expérience (XDM) standard qui décrit un contact ou un prospect associé à une campagne commerciale. |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


La relation entre les schémas de recherche B2B, le schéma de profil et le schéma d’événement est définie dans la configuration B2B d’Experience Platform. Voir Schémas dans [Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) et [Définition d’une relation multiple-à-un entre deux schémas dans Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/relationship-b2b).


Pour garantir une configuration correcte d’une connexion qui prend en charge les recherches basées sur les personnes de vos données B2B, utilisez l’illustration suivante pour obtenir un aperçu et procédez comme suit :

![Schémas B2B annotés](assets/b2b-schemas-annotated.svg)

1. Ajoutez des jeux de données du tableau ci-dessus à votre connexion.
1. Pour chaque jeu de données de recherche que vous ajoutez à votre connexion, vous devez définir explicitement la relation avec un jeu de données d’événement à l’aide de la **[!UICONTROL clé]** et de la **[!UICONTROL clé de correspondance]** dans la boîte de dialogue **[!UICONTROL Modifier le jeu de données]**.
1. Pour chaque jeu de données de recherche que vous souhaitez transformer pour les recherches B2B basées sur des personnes, activez l’option **[!UICONTROL Transformer le jeu de données]** pour vous assurer que les données sont transformées pour les recherches basées sur des personnes. Pour plus d’informations, voir [Transformation des jeux de données pour les recherches B2B](/help/connections/transform-datasets-b2b-lookups.md) .

   ![Clé - Clé correspondante](assets/key-matchingkey.png)

   Le tableau ci-dessous fournit un exemple d’aperçu des valeurs [!UICONTROL ID de personne], [!UICONTROL Clé] et [!UICONTROL Clé correspondante] pour chacun des jeux de données.

   | Jeu de données | ID de personne | Clé | Correspondance de la clé <br/> (dans le jeu de données d’événement) |
   |---|---|---|---| 
   | Jeu de données d’activité B2B | SourceKey <br/>**personKey.sourceKey** | | |
   | Jeu de données de personne B2B | SourceKey <br/>**b2b.personKey.sourceKey** | | |
   | Jeu de données de compte B2B | | SourceKey <br/>**accountKey.sourceKey**❶ | SourceKey<br>(Jeu de données de personne B2B)<br/>**b2b.accountKey.sourceKey**❶ |
   | Jeu de données d’opportunité B2B | | Clé Source <br/>**opportunitésKey.sourceKey**❷ | SourceKey<br/>(Jeu de données de relation d’opportunité B2B)<br/>**opportunitésKey.sourceKey**❷ |
   | Jeu de données de campagne B2B | | SourceKey <br/>**campaignKey.sourceKey**❸ | SourceKey<br/>(Jeu de données de membre de campagne B2B)<br/>**campaignKey.sourceKey**❸<br/> |
   | Jeu de données de liste marketing B2B | | SourceKey <br/>**marketingListKey.sourceKey**❹ | SourceKey<br/>(Jeu de données de membre de liste marketing B2B)<br/>**marketingListKey.sourceKey**❹ |
   | Jeu de données sur la relation de personne de compte B2B | | SourceKey <br/>**personKey.sourceKey**❺ | Clé Source<br/>(Jeux de données d’événement)<br/>**personKey.sourceKey**❺ |
   | Jeu de données de relation d’opportunité B2B | | SourceKey <br/>**personKey.sourceKe** y ❻ | Clé Source<br/>(Jeux de données d’événement)<br/>**personKey.sourceKey**❻ |
   | Jeu de données des membres de campagne B2B | | SourceKey <br/>**personKey.sourceKey**❼ | Clé Source<br/>(Jeux de données d’événement)<br/>**personKey.sourceKey**❼ |
   | Jeu de données des membres de liste marketing B2B | | SourceKey <br/>**personKey.sourceKey**❽ | Clé Source<br/>(Jeux de données d’événement)<br/>**personKey.sourceKey**❽ |

{style="table-layout:auto"}

Voir [Ajout et configuration de jeux de données](../../connections/create-connection.md) pour plus d’informations sur la configuration des paramètres d’un jeu de données.


## Vue de données

Pour avoir accès aux dimensions et mesures B2B appropriées lors de la création de votre projet Workspace, vous devez définir votre vue de données en conséquence.

Vous pouvez, par exemple, ajouter les composants suivants à votre vue de données pour vous assurer que vous pouvez créer des rapports sur le niveau basé sur la personne sur vos données B2B. Les noms des composants sont parfois modifiés pour plus de clarté à partir de leurs noms de schéma d’origine.

+++Mesures

| Nom du composant | Jeu de données | Type de données | Chemin du schéma |
|---|---|---|---|
| Recettes annuelles du compte | Jeu de données de compte B2B | Double | accountOrganization.annualRevenue.amount |
| Nombre d’employés | Jeu de données de compte B2B | Nombre entier | accountOrganization.numberOfEmployees |
| Coût réel de la campagne | Jeu de données de campagne B2B | Double | actualCost.amount |
| Coût de la campagne budgété | Jeu de données de campagne B2B | Double | budgetedCost.amount |
| Recettes attendues sur les opportunités | Jeu de données d’opportunité B2B | Double | expectedRevenue.amount |
| Recettes de campagne attendues | Jeu de données de campagne B2B | Double | expectedRevenue.amount |
| Montant de l’opportunité | Jeu de données d’opportunité B2B | Double | opportunityAmount.amount |

+++

+++Dimensions

| Nom du composant | Jeu de données | Type de données | Chemin du schéma |
|---|---|---|---|
| Nom de compte | Jeu de données de compte B2B | Chaîne | accountName |
| Nom de la campagne | Jeu de données de campagne B2B | Chaîne | campaignName |
| Nom du canal | Jeu de données de campagne B2B | Chaîne | channelName |
| Pays | Jeu de données de compte B2B | Chaîne | accountBillingAddress.country |
| Nom de la catégorie de prévisions | Jeu de données d’opportunité B2B | Chaîne | forecastCategoryName |
| Secteur industriel | Jeu de données de compte B2B | Chaîne | accountOrganization.industry |
| Nom | Jeu de données de personne B2B | Chaîne | person.name.lastName |
| Nom de la liste marketing | Jeu de données de liste marketing B2B | Chaîne | marketingListName |
| Nom de l’opportunité | Jeu de données d’opportunité B2B | Chaîne | opportunitésName |
| Étape d’opportunité | Jeu de données d’opportunité B2B | Chaîne | opportunitésStage |
| Type d’opportunité | Jeu de données de type d’opportunité B2B | Chaîne | opportunitésType |
| Nom de la session de webinaire | Jeu de données de campagne B2B | Chaîne | webinarSessionName |

+++

## Workspace

Lorsque vos composants sont correctement définis dans la vue de données, vous pouvez désormais créer des rapports B2B et des visualisations spécifiques dans votre projet Workspace.

Vous trouverez ci-dessous une capture d’écran d’un exemple de projet qui repose sur la connexion et la vue de données décrites ci-dessus. Les descriptions de visualisation expliquent laquelle de la visualisation de tableau à structure libre repose sur les données de recherche B2B transformées.

![Exemple de projet](assets/sample-workspace-project.png)

