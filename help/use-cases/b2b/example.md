---
title: Exemple de projet B2B
description: Découvrez comment configurer et générer des rapports sur les données B2B
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 1bfebb53fbe056ed6320380178c8b1ce8f7079f1
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 13%

---

# Exemple de projet B2B basé sur les personnes

Cet article illustre un cas d’utilisation dans lequel vous souhaitez générer correctement des rapports dans Customer Journey Analytics sur les données de personne dans le contexte d’une configuration B2B standard basée sur la personne. Une telle configuration est facilitée par le [B2B edition Real-Time CDP](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview).  Le cas d’utilisation explique comment configurer et générer des rapports sur les données B2B basées sur le niveau du profil (personne) dans Customer Journey Analytics.

[!BADGE B2B edition ]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} une section distincte pour les cas d’utilisation de création de rapports basés sur les comptes est publiée avec la version de [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md).

## Connexion

Définissez votre connexion pour inclure tous les jeux de données B2B pertinents d’Experience Platform. Jeux de données que vous pouvez envisager d’ajouter à votre connexion :

| Jeu de données | Schéma | Type de schéma | Classe de base | Description |
|---|---|---|---|---|
| Jeu De Données D’Activité B2B | Schéma D’Activité B2B | Événement | XDM ExperienceEvent | Un ExperienceEvent est un enregistrement factuel de ce qui s’est produit, y compris le moment de survenue et l’identité de la personne concernée. Les modèles ExperienceEvent peuvent être explicites (actions humaines directement observables) ou implicites (obtenus sans action humaine directe), et sont enregistrés sans agrégation ni interprétation. Les événements d’expérience sont essentiels pour l’analyse de domaine temporel, car ils permettent l’observation et l’analyse des modifications qui se produisent dans une fenêtre de temps donnée, ainsi que la comparaison entre plusieurs fenêtres de temps pour suivre les tendances. |
| Jeu De Données De Personnes B2B | Schéma de personne B2B | Profile | XDM Individual Profile | Un profil individuel XDM constitue une représentation unique des attributs et des centres d’intérêt des individus identifiés et partiellement identifiés. Les profils moins identifiés peuvent contenir uniquement des signaux comportementaux anonymes, tels que des cookies de navigateur, tandis que les profils hautement identifiés peuvent contenir des informations personnelles détaillées, telles que le nom, la date de naissance, l’emplacement et l’adresse e-mail. À mesure qu’un profil se développe, il devient un solide référentiel d’informations personnelles, d’informations d’identification, de coordonnées et de préférences de communication pour une personne. |
| Jeu De Données De Compte B2B | Schéma de compte B2B | Recherche | Compte d’entreprise XDM | Un compte professionnel XDM est une classe XDM (modèle de données d’expérience) standard qui capture les propriétés minimales requises d’un compte professionnel. Cette classe XDM peut uniquement être incluse dans le profil pour les clients avec l’édition B2B ou B2P. |
| Jeu de données d’opportunité B2B | Schéma d’opportunité B2B | Recherche | XDM Business Opportunity | XDM Business Opportunity est une classe de modèle de données d’expérience (XDM) standard qui capture les propriétés minimales requises d’une opportunité commerciale. Cette classe XDM peut uniquement être incluse dans le profil pour les clients avec l’édition B2B ou B2P. |
| Jeu De Données De Campagne B2B | Schéma De Campagne B2B | Recherche | XDM Business Campaign | XDM Business Campaign est une classe XDM (modèle de données d’expérience) standard qui capture les propriétés minimales requises d’une campagne commerciale. Cette classe XDM peut uniquement être incluse dans le profil pour les clients avec l’édition B2B ou B2P. |
| Jeu De Données De Liste Marketing B2B | Schéma de liste marketing B2B | Recherche | Liste XDM Business Marketing | La liste XDM Business Marketing est une classe XDM (modèle de données d’expérience) standard qui capture les propriétés minimales requises d’une liste marketing. Les listes marketing vous permettent de donner la priorité aux prospects qui sont les plus susceptibles d’acheter votre produit. Cette classe XDM peut uniquement être incluse dans le profil pour les clients avec l’édition B2B ou B2P. |
| Jeu De Données Relation Personne-Compte B2B | Schéma De Relation Entre La Personne Et Le Compte B2B | Recherche | Relation Personne/Compte d’entreprise XDM | La relation de la personne avec le compte professionnel XDM est une classe XDM standard qui capture les propriétés minimales requises d’une personne associée à un compte professionnel. |
| Jeu De Données De Relation De La Personne Avec L’Opportunité B2B | Schéma de relation de la personne avec l’opportunité B2B | Recherche | Relation Personne/XDM Business Opportunity | La relation de la personne avec l’opportunité commerciale XDM est une classe XDM (modèle de données d’expérience) standard qui capture les propriétés minimales requises d’une personne associée à une opportunité commerciale. |
| Jeu De Données De Membre De La Liste Marketing B2B | Schéma des membres de la liste marketing B2B | Recherche | Membres de la liste marketing XDM | Membres de la liste marketing professionnelle XDM est une classe XDM (modèle de données d’expérience) standard qui décrit les membres, les personnes ou les contacts associés à une liste marketing. |
| Jeu De Données De Membre De Campagne B2B | Schéma des membres de la campagne B2B | Recherche | Membres de XDM Business Campaign | Membres de XDM Business Campaign est une classe XDM (modèle de données d’expérience) standard qui décrit un contact ou un prospect associé à une campagne commerciale. |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


La relation entre les schémas de recherche B2B, le schéma de profil et le schéma d’événement est définie dans la configuration B2B d’Experience Platform. Voir Schémas dans [Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/fr/docs/experience-platform/rtcdp/schemas/b2b) et [Définir une relation multiple-à-un entre deux schémas dans Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/relationship-b2b).


Pour garantir une configuration appropriée d’une connexion qui prend en charge les recherches basées sur la personne de vos données B2B, utilisez l’illustration suivante pour obtenir un aperçu et procédez comme suit :

![Schémas B2B annotés](assets/b2b-schemas-annotated.svg)

1. Ajoutez des jeux de données du tableau ci-dessus à votre connexion.
1. Pour chaque jeu de données de recherche que vous ajoutez à votre connexion, vous devez définir explicitement la relation avec un jeu de données d’événement à l’aide de la **[!UICONTROL Clé]** et de la **[!UICONTROL Clé correspondante]** dans la boîte de dialogue **[!UICONTROL Modifier le jeu de données]**.
1. Pour chaque jeu de données de recherche que vous souhaitez transformer pour les recherches B2B basées sur la personne, activez **[!UICONTROL Transformer le jeu de données]** afin de vous assurer que les données sont transformées pour les recherches basées sur la personne. Consultez [ Transformer des jeux de données pour les recherches B2B ](/help/connections/transform-datasets-b2b-lookups.md) pour plus d’informations.

   ![Key - Clé correspondante](assets/key-matchingkey.png)

   Le tableau ci-dessous présente un exemple de présentation des valeurs [!UICONTROL ID de personne], [!UICONTROL Clé] et [!UICONTROL Clé correspondante] pour chacun des jeux de données.

   | Jeu de données | ID de personne | Clé | Clé correspondante<br/>(dans le jeu de données de l’événement) |
   |---|---|---|---| 
   | Jeu De Données D’Activité B2B | SourceKey <br/>**personKey.sourceKey** | | |
   | Jeu De Données De Personnes B2B | SourceKey <br/>**b2b.personKey.sourceKey** | | |
   | Jeu De Données De Compte B2B | | SourceKey <br/>**accountKey.sourceKey**❶ | SourceKey<br>(Jeu de données de personne B2B)<br/>**b2b.accountKey.sourceKey**❶ |
   | Jeu de données d’opportunité B2B | | Source Key <br/>**opportunitéKey.sourceKey**❷ | SourceKey<br/>(jeu de données de relation d’opportunité B2B)<br/>**opportunitéKey.sourceKey**❷ |
   | Jeu De Données De Campagne B2B | | SourceKey <br/>**campaignKey.sourceKey**❸ | SourceKey<br/>(jeu de données de membre de campagne B2B)<br/>**campaignKey.sourceKey**❸<br/> |
   | Jeu De Données De Liste Marketing B2B | | SourceKey <br/>**marketingListKey.sourceKey**❹ | SourceKey<br/>(jeu de données de membre de la liste marketing B2B)<br/>**marketingListKey.sourceKey**❹ |
   | Jeu De Données Relation Personne-Compte B2B | | SourceKey <br/>**personKey.sourceKey**❺ | Clé Source<br/>(jeux de données d’événements)<br/>**personKey.sourceKey**❺ |
   | Jeu De Données De Relation De La Personne Avec L’Opportunité B2B | | SourceKey <br/>**personKey.sourceKe** y❻ | Clé Source<br/>(jeux de données d’événements)<br/>**personKey.sourceKey**❻ |
   | Jeu De Données De Membre De Campagne B2B | | SourceKey <br/>**personKey.sourceKey**❼ | Clé Source<br/>(jeux de données d’événements)<br/>**personKey.sourceKey**❼ |
   | Jeu De Données De Membre De La Liste Marketing B2B | | SourceKey <br/>**personKey.sourceKey**❽ | Clé Source<br/>(jeux de données d’événements)<br/>**personKey.sourceKey**❽ |

{style="table-layout:auto"}

Voir [Ajouter et configurer des jeux de données](../../connections/create-connection.md) pour plus d’informations sur la configuration des paramètres d’un jeu de données.


## Vue de données

Pour avoir accès aux dimensions et mesures B2B pertinentes lors de la création de votre projet Workspace, vous devez définir votre vue de données en conséquence.

Vous pouvez, par exemple, ajouter les composants suivants à votre vue de données pour vous assurer que vous pouvez créer des rapports au niveau de la personne sur vos données B2B. Les noms des composants sont parfois modifiés par souci de clarté à partir de leurs noms de schéma d’origine.

+++Mesures 

| Nom du composant | Jeu de données | Type de données | Chemin du schéma |
|---|---|---|---|
| Chiffre d’affaires du compte annuel | Jeu De Données De Compte B2B | Double | accountOrganization.annualRevenue.amount |
| Nombre d’employés | Jeu De Données De Compte B2B | Nombre entier | accountOrganization.numberOfEmployees |
| Coût réel de la campagne | Jeu De Données De Campagne B2B | Double | actualCost.amount |
| Coût budgété de la campagne | Jeu De Données De Campagne B2B | Double | budgetedCost.amount |
| Chiffre d’affaires d’opportunité attendu | Jeu de données d’opportunité B2B | Double | expectedRevenue.amount |
| Chiffre d’affaires de campagne attendu | Jeu De Données De Campagne B2B | Double | expectedRevenue.amount |
| Montant de l’opportunité | Jeu de données d’opportunité B2B | Double | opportunityAmount.amount |

+++

+++Dimensions

| Nom du composant | Jeu de données | Type de données | Chemin du schéma |
|---|---|---|---|
| Nom de compte | Jeu De Données De Compte B2B | Chaîne | accountName |
| Nom de la campagne | Jeu De Données De Campagne B2B | Chaîne | campaignName |
| Nom du canal | Jeu De Données De Campagne B2B | Chaîne | channelName |
| Pays | Jeu De Données De Compte B2B | Chaîne | accountBillingAddress.country |
| Nom de la catégorie de prévision | Jeu de données d’opportunité B2B | Chaîne | forecastCategoryName |
| Secteur industriel | Jeu De Données De Compte B2B | Chaîne | accountOrganization.industry |
| Nom | Jeu De Données De Personnes B2B | Chaîne | person.name.lastName |
| Nom de la liste marketing | Jeu De Données De Liste Marketing B2B | Chaîne | marketingListName |
| Nom de l’opportunité | Jeu de données d’opportunité B2B | Chaîne | nom de l’opportunité |
| Étape de l’opportunité | Jeu de données d’opportunité B2B | Chaîne | étape de l’opportunité |
| Type d’opportunité | Jeu De Données De Type D’Opportunité B2B | Chaîne | type d’opportunité |
| Nom de la session du webinaire | Jeu De Données De Campagne B2B | Chaîne | webinarSessionName |

+++

## Workspace

Une fois les composants correctement définis dans la vue de données, vous pouvez créer des rapports et des visualisations B2B spécifiques dans votre projet Workspace.

Voici une capture d’écran d’un exemple de projet qui repose sur la connexion et la vue de données décrites ci-dessus. Les descriptions des visualisations expliquent laquelle des visualisations des tableaux à structure libre repose sur les données de recherche B2B transformées.

![Exemple de projet](assets/sample-workspace-project.png)

