---
title: (B2B) Ajouter des données au niveau du compte en tant que jeu de données de recherche
description: Découvrez comment ajouter des données basées sur un compte en tant que jeu de données de recherche à CJA
translation-type: tm+mt
source-git-commit: e3d4a672c33b8c536246836a062d544e3d5b8a01
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 2%

---


# (B2B) Ajouter des données au niveau du compte en tant que jeu de données de recherche

Ce cas d’utilisation B2B vous montre comment spécifier vos données au niveau du compte plutôt qu’au niveau de la personne pour l’analyse. L’analyse au niveau du compte peut répondre à des questions telles que

* Quel nom de société correspond à ce compte ?
* Combien d&#39;employés sont associés à ce compte/cette société ?
* Quels rôles y a-t-il dans ce compte ?
* Comment ce compte fonctionne-t-il dans son ensemble par rapport à une campagne marketing spécifique, par rapport à un autre compte ?
* Certains rôles (tels que celui de responsable informatique) se comportent-ils différemment d&#39;un compte à l&#39;autre ?

Pour ce faire, vous devez intégrer les informations au niveau du compte sous la forme [recherche](/help/getting-started/cja-glossary.md) jeu de données (semblable aux classifications en Adobe Analytics traditionnel).

Vous commencez par créer un schéma de recherche dans Adobe Experience Platform, puis vous créez un ensemble de données de table de recherche en ingérant des données au niveau du compte .csv. Ensuite, vous allez créer une connexion CJA qui combine différents jeux de données, y compris la recherche que vous avez créée. Vous pouvez ensuite créer une vue de données et enfin utiliser toutes ces données dans Workspace.

>[!NOTE]
>
>La taille des tables de recherche peut atteindre 1 Go.

## 1. Créer un schéma de recherche (Experience Platform)

Création de votre propre schéma pour le [recherche](/help/getting-started/cja-glossary.md) garantit que le jeu de données utilisé sera disponible dans CJA avec la configuration correcte (type d&#39;enregistrement). La bonne pratique consiste à [créer une classe de schéma personnalisée](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) appelée &quot;Recherche&quot;, vide de tout élément, qui peut être réutilisé pour toutes les tables de recherche.

![](assets/create-new-class.png)

## 2. Créer un jeu de données de recherche (Experience Platform)

Une fois le schéma créé, vous devez créer un jeu de données de recherche à partir de ce schéma, dans Experience Platform. Ce jeu de données de recherche contient des informations marketing au niveau du compte, telles que : Nom de la société, nombre total d&#39;employés, nom de domaine, à quel secteur ils appartiennent, recettes annuelles, qu&#39;ils soient clients actuels ou non de l&#39;Experience Platform, quelle étape de vente ils se trouvent, quelle équipe du compte utilise CJA, etc.

1. Dans Adobe Experience Platform, accédez à **[!UICONTROL data Management > Jeu de données]**.
1. Cliquez sur **[!UICONTROL + Créer un jeu de données]**.
1. Cliquez sur **[!UICONTROL Créer un jeu de données à partir d&#39;un schéma]**.
1. Sélectionnez la classe de Schéma de recherche que vous avez créée.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. Nommez le jeu de données (dans notre exemple, B2B Info) et fournissez une description.
1. Cliquez sur **[!UICONTROL Terminer]**.

## 3. Envoi de données dans l&#39;Experience Platform

Instructions sur la manière de procéder [Mappage d’un fichier CSV à un schéma XDM](https://docs.adobe.com/content/help/en/experience-platform/ingestion/tutorials/map-a-csv-file.html) doit être utile si vous utilisez un fichier CSV.

[Autres méthodes](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.html) sont également disponibles.

Lors de l&#39;intégration des données et de l&#39;établissement de la recherche, il faut environ 2 à 4 heures, selon la taille de la table de recherche.

## 4. Combiner des jeux de données dans une connexion (Customer Journey Analytics)

Pour cet exemple, nous combinons 3 jeux de données en une connexion CJA :

| Nom du jeu de données | Description | Classe de Schéma AEP | Informations sur le jeu de données |
|---|---|---|---|
| Impression B2B | Contient des données au niveau du événement et du parcours de navigation au niveau du compte. Par exemple, il contient l’adresse électronique et l’ID de compte correspondant, ainsi que le nom marketing, pour l’exécution des publicités marketing. Il comprend également les impressions pour ces publicités, par utilisateur. | Basé sur la classe de schéma XDM ExperienceEvent | Le `emailID` est utilisée comme identité Principale et un `Customer ID` espace de nommage. Par conséquent, il s’affiche comme valeur par défaut. **[!UICONTROL ID de personne]** en Customer Journey Analytics. ![Impressions](assets/impressions-mixins.png) |
| Profil B2B | Ce jeu de données de profil vous en dit plus sur les utilisateurs d’un compte, tels que le titre de leur travail, le compte auquel ils appartiennent, leur profil LinkedIn, etc. | Basé sur la classe de schéma de Profil individuel XDM | Pas besoin de sélectionner `emailID` comme Principal ID dans ce schéma. Veillez à activer **[!UICONTROL Profil]**; si vous ne le faites pas, CJA ne sera pas en mesure de connecter la variable `emailID` dans le Profil B2B avec la variable `emailID` dans les données d’impression B2B. (Cette fonctionnalité s’appelle l’assemblage sur le terrain.) ![Profil](assets/profile-mixins.png) |
| Infos B2B | Voir &quot;Créer un jeu de données de recherche&quot; ci-dessus. | B2BAccount (classe de schéma de recherche personnalisée) | La relation entre `accountID` et le jeu de données Impressions B2B a été automatiquement créé en connectant le jeu de données Info B2B au jeu de données Impression B2B dans CJA, comme décrit dans les étapes ci-dessous. ![Recherche](assets/lookup-mixins.png) |

Voici comment combiner les jeux de données :

1. Dans le Customer Journey Analytics, sélectionnez la variable **[!UICONTROL Connexions]** .
1. Sélectionnez les jeux de données (dans notre exemple, les trois ci-dessus) que vous souhaitez combiner.
1. Pour le jeu de données Info B2B, sélectionnez la variable `accountID` qui sera utilisée dans votre table de choix. Sélectionnez ensuite sa clé correspondante (dimension correspondante), `accountID` dans votre jeu de données de événement.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. Nommez et décrivez la connexion et configurez-la en fonction de [ces instructions](/help/connections/create-connection.md).
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## 5. Créez une vue de données à partir de cette connexion.

Suivez les instructions de la section [création de visionneuses de données](/help/data-views/create-dataview.md).

* ajoutez tous les composants (dimensions et mesures) dont vous avez besoin dans les jeux de données.

## 6. Analyse des données dans Workspace

Vous pouvez désormais créer des projets Workspace basés sur les données des trois jeux de données.

Par exemple, vous pouvez trouver des réponses aux questions posées dans l’introduction :

* Ventilez l’ID de courrier électronique par ID de compte pour déterminer à quelle société appartient un ID de courrier électronique.
* Combien d&#39;employés sont associés à un ID de compte spécifique ?
* À quel secteur appartient un ID de compte ?

![](assets/project-lookup.png)
