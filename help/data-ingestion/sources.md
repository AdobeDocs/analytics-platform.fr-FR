---
title: Ingestion et utilisation de données à l’aide des connecteurs source
description: expliquer comment ingérer et utiliser des données à l’aide des connecteurs source dans Customer Journey Analytics ;
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f910f8e810c5c5d6f4d43aff2b609d8bf6c131ca
workflow-type: tm+mt
source-wordcount: '1952'
ht-degree: 6%

---


# Ingérez et utilisez des données à l’aide des connecteurs source.

Ce guide de démarrage rapide explique comment ingérer des données dans Adobe Experience Platform à l’aide d’un connecteur source vers un fournisseur de données, puis les utiliser dans Customer Journey Analytics.

Pour ce faire, vous devez :

- **Configuration d’un schéma et d’un jeu de données** dans Adobe Experience Platform pour définir le modèle (schéma) des données que vous souhaitez collecter et l’emplacement où les collecter réellement (jeu de données).

- **Utilisation d’un connecteur source** dans Adobe Experience Platform pour placer vos données dans le jeu de données configuré.

- **Configurer une connexion** en Customer Journey Analytics. Cette connexion doit (au moins) inclure votre jeu de données Adobe Experience Platform.

- **Configuration d’une vue de données** dans Customer Journey Analytics pour définir les mesures et la dimension que vous souhaitez utiliser dans Analysis Workspace.

- **Configuration d’un projet** dans Customer Journey Analytics pour créer vos rapports et visualisations.



>[!NOTE]
>
>Il s’agit d’un guide simplifié sur la manière d’ingérer des données à l’aide d’un connecteur source dans Adobe Experience Platform et de les utiliser dans Customer Journey Analytics.  Il est vivement recommandé d’étudier les informations supplémentaires lorsqu’elles y sont référencées.


## Configuration d’un schéma et d’un jeu de données

Pour ingérer des données dans Adobe Experience Platform, vous devez d’abord définir les données à collecter. Toutes les données ingérées dans Adobe Experience Platform doivent être conformes à une structure standard dénormalisée afin qu’elles soient reconnues et exploitées par les fonctionnalités et fonctionnalités en aval. Le modèle de données d’expérience (XDM) est la structure standard qui fournit cette structure sous la forme de schémas.

Une fois que vous avez défini un schéma, vous utiliserez un ou plusieurs jeux de données pour stocker et gérer la collecte de données. Un jeu de données est une structure de stockage et de gestion pour la collecte de données, généralement sous la forme d&#39;un tableau, qui contient un schéma (des colonnes) et des champs (des lignes).

Toutes les données ingérées dans Adobe Experience Platform doivent être conformes à un schéma prédéfini avant de pouvoir être conservées en tant que jeu de données.

### Configuration d’un schéma

Pour ce démarrage rapide, nous supposons que vous souhaitiez collecter certaines données de fidélité, par exemple l’identifiant de fidélité, les points de fidélité et l’état de fidélité.
Pour cela, vous devez d’abord définir un schéma qui modélise ces données.

Pour configurer votre schéma :

1. Dans l’interface utilisateur de Adobe Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Schémas]** dans [!UICONTROL GESTION DES DONNÉES].

2. Sélectionner **[!UICONTROL Créer un schéma]**. Sélectionner **[!UICONTROL XDM Individual Profile]** dans la liste des options.

   ![Création d’un schéma](./assets/create-schema.png)

   >[!INFO]
   >
   >    Un schéma de profil individuel est utilisé pour modéliser le profil. _Attributs_ (nom, email, genre, etc.). Un schéma d’événement d’expérience est utilisé pour modéliser la variable _comportement_ d’un profil (comme une page vue, ajouter au panier).


3. Dans le [!UICONTROL Schéma sans titre] écran :

   1. Saisissez un nom d’affichage pour votre schéma et (facultatif) une description.

      ![Nommer votre schéma](./assets/name-loyalty-schema.png)

   2. Sélectionner **[!UICONTROL + Ajouter]** in [!UICONTROL Groupes de champs].

      ![Ajouter un groupe de champs](./assets/add-field-group-button.png)

      Les groupes de champs sont une collection d’objets et d’attributs réutilisables qui vous permet d’étendre facilement vos schémas.

   3. Dans le [!UICONTROL Ajouter des groupes de champs] , sélectionnez **[!UICONTROL Détails de fidélité]** groupe de champs de la liste.

      ![Groupe de champs ExperienceEvent du SDK Web AEP](./assets/loyalty-fieldgroup.png)

      Vous pouvez sélectionner le bouton Aperçu pour afficher un aperçu des champs qui font partie de ce groupe de champs.

      ![Aperçu du groupe de champs ExperienceEvent du SDK Web AEP](./assets/loyalty-fieldgroup-preview.png)

      Sélectionner **[!UICONTROL Précédent]** pour fermer l’aperçu.

   4. Sélectionner **[!UICONTROL Ajouter des groupes de champs]**.

4. Sélectionner **[!UICONTROL +]** en regard de votre nom de schéma dans la variable [!UICONTROL Structure] du panneau.

   ![Bouton Exemple de schéma Ajouter un champ](./assets/example-loalty-schema-plus.png)

5. Dans le [!UICONTROL Propriétés du champ] panneau, entrée `Identification` comme nom, **[!UICONTROL Identification]** comme la propriété [!UICONTROL Nom d’affichage], sélectionnez **[!UICONTROL Objet]** comme la propriété [!UICONTROL Type] et sélectionnez **[!UICONTROL Profile Core v2]** comme la propriété [!UICONTROL Groupe de champs].

   ![Objet d’identification](./assets/identifcation-loyalty-field.png)

   Cela ajoute des fonctionnalités d’identification à votre schéma. Dans votre cas, vous souhaitez identifier les informations de fidélité à l’aide de l’adresse électronique dans vos données de lot.

   Sélectionner **[!UICONTROL Appliquer]** pour ajouter cet objet à votre schéma.

6. Sélectionnez la **[!UICONTROL email]** dans l’objet d’identification que vous venez d’ajouter, puis sélectionnez **[!UICONTROL Identité]** et **[!UICONTROL Email]** de la [!UICONTROL Espace de noms d’identité] dans le [!UICONTROL Propriétés du champ] du panneau.

   ![Définition de l’identité de l’email](./assets/specify-email-loyalty-id.png)

   Vous spécifiez l’adresse électronique comme identité que le service Adobe Experience Platform Identity peut utiliser pour combiner (assembler) le comportement des profils.

   Sélectionner **[!UICONTROL Appliquer]**. Une icône d’empreinte apparaît dans l’attribut email.

7. Sélectionnez le niveau racine de votre schéma (avec le nom du schéma), puis sélectionnez l’option **[!UICONTROL Profil]** changer.

   Vous serez invité à activer le schéma pour le profil. Une fois activées, lorsque les données sont ingérées dans des jeux de données basés sur ce schéma, ces données sont fusionnées dans le profil client en temps réel.

   Voir [Activation du schéma à utiliser dans Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) pour plus d’informations.

   >[!IMPORTANT]
   >
   >    Une fois que vous avez enregistré un schéma activé pour le profil, il ne peut plus être désactivé pour le profil.

   ![Activation du schéma pour le profil](./assets/enable-for-profile.png)

8. Sélectionner **[!UICONTROL Enregistrer]** pour enregistrer votre schéma.

Vous avez créé un schéma minimal qui modélise les données de fidélité que vous pouvez ingérer dans Adobe Experience Platform. Le schéma permet d&#39;identifier les profils à l&#39;aide de l&#39;adresse email. En activant le schéma pour le profil, vous vous assurez que les données de votre source de diffusion en continu sont ajoutées au profil client en temps réel.

Voir [Création et modification de schémas dans l’interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=fr) pour plus d’informations sur l’ajout et la suppression de groupes de champs et de champs individuels dans un schéma.

### Configuration d’un jeu de données

Avec votre schéma, vous avez défini votre modèle de données. Vous devez maintenant définir le concept pour stocker et gérer ces données. Cela se fait par le biais de jeux de données.

Pour configurer votre jeu de données :

1. Dans l’interface utilisateur de Adobe Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Jeux de données]** dans [!UICONTROL GESTION DES DONNÉES].

2. Sélectionner **[!UICONTROL Création d’un jeu de données]**.

   ![Création d’un jeu de données](./assets/create-dataset.png)

3. Sélectionnez **[!UICONTROL Créer un jeu de données à partir d&#39;un schéma]**.

   ![Créer un jeu de données à partir d’un schéma](./assets/create-dataset-from-schema.png)

4. Sélectionnez le schéma que vous avez créé précédemment et sélectionnez **[!UICONTROL Suivant]**.

5. Nommez votre jeu de données et (facultatif) fournissez une description.

   ![Nom du jeu de données](./assets/name-your-datatest.png)

6. Sélectionner **[!UICONTROL Terminer]**.

7. Sélectionnez la **[!UICONTROL Profil]** changer.

   Vous serez invité à activer le jeu de données pour le profil. Une fois activé, le jeu de données enrichit les profils clients en temps réel avec ses données ingérées.

   >[!IMPORTANT]
   >
   >    Vous pouvez uniquement activer un jeu de données pour le profil lorsque le schéma auquel le jeu de données adhère est également activé pour le profil.

   ![Activation du schéma pour le profil](./assets/loyalty-dataset-profile.png)

Voir [Guide de l’interface utilisateur des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr) pour plus d’informations sur l’affichage, la prévisualisation, la création et la suppression d’un jeu de données. Comment activer un jeu de données pour Real-time Customer Profile.


## Utilisation d’un connecteur source

Selon l’endroit où vous recevez les données de fidélité, vous choisissez le connecteur source approprié disponible dans Adobe Experience Platform.

Pour configurer un connecteur source :

1. Dans l’interface utilisateur de Adobe Experience Platform, sélectionnez **[!UICONTROL Sources]** de [!UICONTROL CONNEXIONS] dans le rail de gauche.

2. Sélectionnez votre connecteur source dans la liste des connecteurs source disponibles. Chaque connecteur suit un workflow similaire :

   - **[!UICONTROL Authentification]**. Vous fournissez des détails d’authentification pour accéder à la source de données.

   - **[!UICONTROL Sélectionner des données]**: Vous sélectionnez les données source à ingérer.

   - **[!UICONTROL Détails du flux de données]**: Vous fournissez des détails supplémentaires sur le flux de données, c’est-à-dire le nom et le jeu de données à utiliser.

   - **[!UICONTROL Mappage]**: Vous mappez les champs de données source entrants aux attributs du schéma associé au jeu de données que vous avez sélectionné.

   - **[!UICONTROL Planification]**: Si possible, vous pouvez planifier l’ingestion des données.

   - **[!UICONTROL Réviser]**: Avant de terminer la configuration, vous devez examiner la définition du connecteur source.

   Chaque connecteur fournit une documentation détaillée.

   Pour accéder à cette documentation :

   - Sur la mosaïque du connecteur, sélectionnez l’option **[!UICONTROL ...]** en regard de [!UICONTROL Configuration] ou [!UICONTROL Ajouter des données].

      ![Afficher la documentation](./assets/sourceconnector-documentation.png)

   - Sélectionner **[!UICONTROL Afficher la documentation]**.


Voir [Ingestion et utilisation de données à partir d’Adobe Analytics traditionnel](./analytics.md) utilisation du connecteur source Adobe Analytics.

Voir [Ingestion et utilisation de données de diffusion en continu](./streaming.md) Découvrez comment utiliser le connecteur source de l’API HTTP.

Voir [Présentation des connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en#terms-and-conditions) pour un aperçu des connecteurs source, y compris des liens vers des informations supplémentaires pour chaque connecteur.


## Configurer une connexion

Pour utiliser les données Adobe Experience Platform dans Customer Journey Analytics, vous créez une connexion qui inclut les données résultant de la configuration de votre schéma, de votre jeu de données et de votre workflow.

Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Espace de travail. Pour générer des rapports sur ces jeux de données, vous devez d’abord établir une connexion entre les jeux de données dans Adobe Experience Platform et Workspace.

Pour créer votre connexion :

1. Dans l’interface utilisateur du Customer Journey Analytics, sélectionnez **[!UICONTROL Connexions]** dans le volet de navigation supérieur.

2. Sélectionner **[!UICONTROL Créer une connexion]**.

3. Dans le [!UICONTROL Connexion sans titre] écran :

   Nommez et décrivez votre connexion dans [!UICONTROL Paramètres de connexion].

   Sélectionnez l’environnement de test approprié dans la [!UICONTROL Sandbox] list in [!UICONTROL Paramètres des données] et sélectionnez le nombre d’événements quotidiens dans la [!UICONTROL Nombre moyen d’événements quotidiens] liste.

   ![Paramètres de connexion](./assets/cja-connections-1.png)

   Sélectionner **[!UICONTROL Ajouter des jeux de données]**.

   Dans le [!UICONTROL Sélectionner des jeux de données] étape [!UICONTROL Ajout de jeux de données]:

   - Sélectionnez le jeu de données que vous avez créé précédemment (`Example Loyalty Dataset`) et tout autre jeu de données que vous souhaitez inclure dans votre connexion.

      ![Ajouter des jeux de données](./assets/cja-connections-2.png)

   - Sélectionnez **[!UICONTROL Suivant]**.
   Dans le [!UICONTROL Paramètres des jeux de données] étape [!UICONTROL Ajout de jeux de données]:

   - Pour chaque jeu de données :

      - Sélectionnez une [!UICONTROL ID de personne] à partir des identités disponibles définies dans les schémas du jeu de données dans Adobe Experience Platform.

      - Sélectionnez la source de données appropriée dans la [!UICONTROL Type de source de données] liste. Si vous spécifiez **[!UICONTROL Autre]** ajoutez ensuite une description pour votre source de données.

      - Définir **[!UICONTROL Importer toutes les nouvelles données]** et **[!UICONTROL Renvoi de données existantes]** selon vos préférences.

      ![Configurer les jeux de données](./assets/cja-connections-3.png)

   - Sélectionner **[!UICONTROL Ajout de jeux de données]**.
   Sélectionnez **[!UICONTROL Enregistrer]**.

Voir [Présentation des connexions](../connections/overview.md) pour plus d’informations sur la création et la gestion d’une connexion, ainsi que sur la sélection et la combinaison de jeux de données.

## Configuration d’une vue de données

Une vue de données est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion. Elle spécifie toutes les dimensions et mesures disponibles dans Analysis Workspace et les colonnes dont ces dimensions et mesures obtiennent leurs données. Les vues de données sont définies en vue de la création de comptes rendus des performances dans Analysis Workspace.

Pour créer votre vue de données :

1. Dans l’interface utilisateur du Customer Journey Analytics, sélectionnez **[!UICONTROL Vues des données]** dans le volet de navigation supérieur.

2. Sélectionner **[!UICONTROL Créer une vue de données]**.

3. Dans le [!UICONTROL Configurer] étape :

   Sélectionnez votre connexion dans le [!UICONTROL Connexion] liste.

   Nom et (éventuellement) description de la connexion.

   ![Configuration de la vue des données](./assets/cja-dataview-1.png)

   Sélectionner **[!UICONTROL Enregistrer et continuer]**.

4. Dans le [!UICONTROL Composants] étape :

   Ajoutez tout champ de schéma et/ou composant standard que vous souhaitez inclure au [!UICONTROL MESURES] ou [!UICONTROL Dimensions] des zones de composant.

   ![Composants de vue de données](./assets/cja-dataview-2.png)

   Sélectionner **[!UICONTROL Enregistrer et continuer]**.

5. Dans le [!UICONTROL Paramètres] étape :

   Paramètres de la ![vue de données](./assets/cja-dataview-3.png)

   Laissez les paramètres tels quels et sélectionnez **[!UICONTROL Enregistrer et terminer]**.

Voir [Présentation des vues des données](../data-views/data-views.md) pour plus d’informations sur la création et la modification d’une vue de données, sur les composants que vous pouvez utiliser dans votre vue de données et sur l’utilisation des paramètres de filtre et de session.


## Configuration d’un projet

Analysis Workspace est un outil de navigation flexible qui vous permet de créer rapidement des analyses et de partager des informations en fonction de vos données. Vous utilisez des projets Workspace pour combiner des composants de données, des tableaux et des visualisations afin de concevoir votre analyse et de la partager avec toute personne de votre entreprise.

Pour créer votre projet :

1. Dans l’interface utilisateur du Customer Journey Analytics, sélectionnez **[!UICONTROL Projets]** dans le volet de navigation supérieur.

2. Sélectionner **[!UICONTROL Projets]** dans le volet de navigation de gauche.

3. Sélectionner **[!UICONTROL Créer un projet]**.

   ![Projet Workspace](./assets/cja-projects-1.png)

   Sélectionner **[!UICONTROL Projet vierge]**.

   ![Workspace - Projet vierge](./assets/cja-projects-2.png)

4. Sélectionnez votre vue de données dans la liste.

   ![Workspace Select Data view](./assets/cja-projects-3.png).

5. Commencez à faire glisser et à déposer des dimensions et des mesures sur le [!UICONTROL Tableau à structure libre] dans le [!UICONTROL Panneau] pour créer votre premier rapport. À titre d’exemple, faites glisser `Program Points Balance` et `Page View` comme mesures et `email` comme dimension pour obtenir un aperçu rapide des profils qui ont visité votre site web et qui font également partie du programme de fidélité collectant des points de fidélité.

   ![Workspace - Premier rapport](./assets/cja-projects-5.png)

Voir [Présentation d’Analysis Workspace](../analysis-workspace/home.md) pour plus d’informations sur la création de projets et la création de votre analyse à l’aide de composants, de visualisation et de panneaux.

>[!SUCCESS]
>
>Vous avez terminé toutes les étapes. En commençant par définir les données de fidélité que vous souhaitez collecter (schéma) et où les stocker (jeu de données) dans Adobe Experience Platform, vous avez configuré le connecteur source approprié pour vous fournir les données de fidélité. Vous avez défini une connexion dans Customer Journey Analytics pour utiliser les données de fidélité ingérées et d’autres données. Votre définition de vue de données vous a permis de spécifier la dimension et les mesures à utiliser. Vous avez enfin créé votre premier projet qui visualise et analyse vos données.
