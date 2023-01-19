---
title: Ingestion des données via le SDK web Adobe Experience Platform et le réseau Edge
description: Expliquer comment ingérer des données dans Customer Parcours Analytics via le SDK Web de Adobe Experience Platform et le réseau Edge
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f910f8e810c5c5d6f4d43aff2b609d8bf6c131ca
workflow-type: tm+mt
source-wordcount: '3591'
ht-degree: 9%

---


# Ingestion des données via le SDK web Adobe Experience Platform et le réseau Edge

Ce guide de démarrage rapide explique comment ingérer des données de suivi de site web directement dans Adobe Experience Platform à l’aide du SDK web Adobe Experience Platform et du réseau Edge, puis les utiliser dans Customer Journey Analytics.

Pour ce faire, vous devez :

- **Configuration d’un schéma et d’un jeu de données** dans Adobe Experience Platform pour définir le modèle (schéma) des données que vous souhaitez collecter et l’emplacement où les collecter réellement (jeu de données).

- **Configuration d’un flux de données** pour configurer Adobe Experience Platform Edge Network afin d’acheminer les données collectées vers le jeu de données que vous avez configuré dans Adobe Experience Platform.

- **Utilisation des balises** pour configurer facilement des règles et des éléments de données par rapport aux données de votre couche de données sur votre site web et vous assurer que les données sont envoyées à la banque de données configurée sur le réseau Edge Adobe Experience Platform.

- **Déploiement et validation**. disposer d’un environnement dans lequel vous pouvez itérer sur le développement des balises. Une fois que tout est validé, publiez-le dans votre environnement de production.

- **Configurer une connexion** en Customer Journey Analytics. Cette connexion doit (au moins) inclure votre jeu de données Adobe Experience Platform.

- **Configuration d’une vue de données** dans Customer Journey Analytics pour définir les mesures et la dimension que vous souhaitez utiliser dans Analysis Workspace.

- **Configuration d’un projet** dans Customer Journey Analytics pour créer vos rapports et visualisations.

>[!NOTE]
>
>Il s’agit d’un guide simplifié sur la manière d’ingérer les données collectées sur votre site dans Adobe Experience Platform et de les utiliser dans Customer Journey Analytics.  Il est vivement recommandé d’étudier les informations supplémentaires lorsqu’elles y sont référencées.


## Configuration d’un schéma et d’un jeu de données

Pour ingérer des données dans Adobe Experience Platform, vous devez d’abord définir les données à collecter. Toutes les données ingérées dans Adobe Experience Platform doivent être conformes à une structure standard dénormalisée afin qu’elles soient reconnues et exploitées par les fonctionnalités et fonctionnalités en aval. Le modèle de données d’expérience (XDM) est la structure standard qui fournit cette structure sous la forme de schémas.

Une fois que vous avez défini un schéma, vous utiliserez un ou plusieurs jeux de données pour stocker et gérer la collecte de données. Un jeu de données est une structure de stockage et de gestion pour la collecte de données, généralement sous la forme d&#39;un tableau, qui contient un schéma (des colonnes) et des champs (des lignes).

Toutes les données ingérées dans Adobe Experience Platform doivent être conformes à un schéma prédéfini avant de pouvoir être conservées en tant que jeu de données.

### Configuration d’un schéma

Vous souhaitez effectuer le suivi de certaines données minimales provenant des profils qui visitent votre site web, par exemple le nom de la page, l’identification, etc.
Pour cela, vous devez d’abord définir un schéma qui modélise ces données.

Pour configurer votre schéma :

1. Dans l’interface utilisateur de Adobe Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Schémas]** dans [!UICONTROL GESTION DES DONNÉES].

2. Sélectionner **[!UICONTROL Créer un schéma]**. Sélectionner **[!UICONTROL XDM ExperienceEvent]** dans la liste des options.

   ![Création d’un schéma](./assets/create-ee-schema.png)

   >[!INFO]
   >
   >    Un schéma d’événement d’expérience est utilisé pour modéliser la variable _comportement_ d’un profil (comme une page vue, ajouter au panier). Un schéma de profil individuel est utilisé pour modéliser le profil. _Attributs_ (nom, email, genre, etc.).


3. Dans le [!UICONTROL Schéma sans titre] écran :

   1. Saisissez un nom d’affichage pour votre schéma et (facultatif) une description.

      ![Nommer votre schéma](./assets/name-schema.png)

   2. Sélectionner **[!UICONTROL + Ajouter]** in [!UICONTROL Groupes de champs].

      ![Ajouter un groupe de champs](./assets/add-field-group-button.png)

      Les groupes de champs sont des collections d’objets et d’attributs réutilisables qui vous permettent d’étendre facilement votre schéma.

   3. Dans le [!UICONTROL Ajouter des groupes de champs] , sélectionnez **[!UICONTROL ExperienceEvent du SDK Web AEP]** groupe de champs de la liste.

      ![Groupe de champs ExperienceEvent du SDK Web AEP](./assets/select-aepwebsdk-experienceevent.png)

      Vous pouvez cliquer sur le bouton Aperçu pour afficher un aperçu des champs qui font partie de ce groupe, par exemple `web > webPageDetails > name`.

      ![Aperçu du groupe de champs ExperienceEvent du SDK Web AEP](./assets/aepwebsdk-experiencevent-preview.png)

      Sélectionner **[!UICONTROL Précédent]** pour fermer l’aperçu.

   4. Sélectionner **[!UICONTROL Ajouter des groupes de champs]**.

4. Sélectionner **[!UICONTROL +]** en regard de votre nom de schéma dans la variable [!UICONTROL Structure] du panneau.

   ![Bouton Exemple de schéma Ajouter un champ](./assets/example-schema-plus.png)

5. Dans le [!UICONTROL Propriétés du champ] panneau, entrée `Identification` comme nom, **[!UICONTROL Identification]** comme la propriété [!UICONTROL Nom d’affichage], sélectionnez **[!UICONTROL Objet]** comme la propriété [!UICONTROL Type] et sélectionnez **[!UICONTROL ExperienceEvent Core v2.1]** comme la propriété [!UICONTROL Groupe de champs].

   ![Objet d’identification](./assets/identification-field.png)

   Cela ajoute des fonctionnalités d’identification à votre schéma. Dans votre cas, vous souhaitez identifier les profils qui visitent votre site à l’aide de l’ID Experience Cloud et de l’adresse électronique. De nombreux autres attributs sont disponibles pour effectuer le suivi de l’identification de votre visiteur (par exemple, l’ID de client, l’ID de fidélité, etc.).

   Sélectionner **[!UICONTROL Appliquer]** pour ajouter cet objet à votre schéma.

6. Sélectionnez la **[!UICONTROL ecid]** dans l’objet d’identification que vous venez d’ajouter, puis sélectionnez **[!UICONTROL Identité]** et **[!UICONTROL Identité Principal]** et **[!UICONTROL ECID]** de la [!UICONTROL Espace de noms d’identité] dans le panneau de droite.

   ![Définition d’ECID comme identité](./assets/specify-identity.png)

   Vous spécifiez l’identité Experience Cloud comme identité Principale que le service Adobe Experience Platform Identity peut utiliser pour combiner (assembler) le comportement des profils avec le même ECID.

   Sélectionner **[!UICONTROL Appliquer]**. Une icône d’empreinte s’affiche dans l’attribut ecid.

7. Sélectionnez la **[!UICONTROL email]** dans l’objet d’identification que vous venez d’ajouter, puis sélectionnez **[!UICONTROL Identité]** et **[!UICONTROL Email]** de la [!UICONTROL Espace de noms d’identité] dans la [!UICONTROL Propriétés du champ] du panneau.

   ![Définition de l’identité de l’email](./assets/specify-email-identity.png)

   Vous spécifiez l’adresse électronique comme autre identité que le service Adobe Experience Platform Identity peut utiliser pour combiner (assembler) le comportement des profils.

   Sélectionner **[!UICONTROL Appliquer]**. Une icône d’empreinte apparaît dans l’attribut email.

   Sélectionnez **[!UICONTROL Enregistrer]**.

8. Sélectionnez l’élément racine de votre schéma qui affiche le nom du schéma, puis sélectionnez l’élément **[!UICONTROL Profil]** changer.

   Vous serez invité à activer le schéma pour le profil. Une fois activées, lorsque les données sont ingérées dans des jeux de données basés sur ce schéma, ces données sont fusionnées dans le profil client en temps réel.

   Voir [Activation du schéma à utiliser dans Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) pour plus d’informations.

   >[!IMPORTANT]
   >
   >    Une fois que vous avez enregistré un schéma activé pour le profil, il ne peut plus être désactivé pour le profil.

   ![Activation du schéma pour le profil](./assets/enable-for-profile.png)

9. Sélectionner **[!UICONTROL Enregistrer]** pour enregistrer votre schéma.

Vous avez créé un schéma minimal qui modélise les données que vous pouvez capturer à partir de votre site web. Le schéma permet d’identifier les profils à l’aide de l’identité et de l’adresse électronique de l’Experience Cloud. En activant le schéma pour le profil, vous vous assurez que les données capturées sur votre site web sont ajoutées au profil client en temps réel.

Outre les données de comportement, vous pouvez également capturer les données d’attribut de profil de votre site (par exemple, les détails des profils s’abonnant à une newsletter).

Pour capturer ces données de profil, vous devez :

- Créez un schéma basé sur la classe XDM Individual Profile.

- Ajoutez le groupe de champs Profile Core v2 au schéma.

- Ajoutez un objet d’identification basé sur le groupe de champs Profile Core v2 .

- Définissez ecid comme identifiant Principal et email comme identifiant.

- Activation du schéma pour le profil

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

   ![Activation du schéma pour le profil](./assets/aepwebsdk-dataset-profile.png)

Voir [Guide de l’interface utilisateur des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=fr) pour plus d’informations sur l’affichage, la prévisualisation, la création et la suppression d’un jeu de données. Comment activer un jeu de données pour Real-time Customer Profile.

## Configuration d’un flux de données

Un flux de données représente la configuration côté serveur lors de la mise en œuvre des SDK web et mobile d’Adobe Experience Platform. Lors de la collecte de données avec les SDK Adobe Experience Platform, les données sont envoyées au réseau Adobe Experience Platform Edge. Il s’agit du flux de données qui détermine à quel(s) service(s) les données sont transférées.

Dans votre configuration, vous souhaitez que les données que vous collectez du site web soient envoyées à votre jeu de données dans Adobe Experience Platform.

Pour configurer votre flux de données :

1. Dans l’interface utilisateur de Adobe Experience Platform, sélectionnez **[!UICONTROL Datastreams]** de [!UICONTROL COLLECTE DE DONNÉES] dans le rail de gauche.

2. Sélectionner **[!UICONTROL Nouvelle structure de données]**.

3. Nommez et décrivez votre flux de données. Sélectionnez votre schéma dans le [!UICONTROL Schéma d’événement] liste.

   ![Nouvelle structure de données](./assets/new-datastream.png)

4. Sélectionnez **[!UICONTROL Enregistrer]**.

5. Sélectionner **[!UICONTROL Ajouter un service]**.

6. Dans le [!UICONTROL Écran Ajouter un service]:

   1. Sélectionner **[!UICONTROL Adobe Experience Platform]** de la [!UICONTROL Service] liste.

   2. Assurez-vous que **[!UICONTROL Activé]** est sélectionnée.

   3. Sélectionnez votre jeu de données dans la [!UICONTROL Jeu de données d’événement] liste.

      ![Service AEP de la chaîne de données](./assets/datastream-aep-service.png)

   4. Laissez les autres paramètres et sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le flux de données.

Votre flux de données est maintenant configuré pour transférer les données collectées sur votre site web vers votre jeu de données dans Adobe Experience Platform.

Voir [Présentation des flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=fr) pour plus d’informations sur la configuration d’un flux de données et la gestion des données sensibles.



## Utilisation des balises

Utilisez la fonction Balises de Adobe Experience Platform pour implémenter du code sur votre site afin de collecter des données. Cette solution de gestion des balises vous permet de déployer le code parallèlement à d’autres exigences de balisage. Les balises offrent une intégration transparente avec Adobe Experience Platform à l’aide de l’extension SDK Web de Adobe Experience Platform.

### Créer votre balise

1. Dans l’interface utilisateur de Adobe Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Balises]** dans [!UICONTROL COLLECTE DE DONNÉES].

2. Sélectionnez **[!UICONTROL Nouvelle propriété]**.

   Nommez la balise, puis sélectionnez **[!UICONTROL Web]** et saisissez un nom de domaine. Sélectionner **[!UICONTROL Enregistrer]** pour continuer.

   ![Création d’une propriété](./assets/create-property.png)

### Configuration de votre balise

Après avoir créé la balise, vous devez la configurer avec les extensions correctes et configurer les éléments de données et les règles en fonction de la manière dont vous souhaitez effectuer le suivi de votre site et envoyer des données à Adobe Experience Platform.

Sélectionnez la balise que vous venez de créer dans la liste de [!UICONTROL Propriétés de balise] pour l’ouvrir.


#### **Extensions**

Vous devez ajouter l’extension SDK Web Adobe Platform à votre balise pour vous assurer que vous pouvez envoyer des données à Adobe Experience Platform (via votre flux de données).

Pour créer et configurer l’extension du SDK Web Adobe Experience Platform :

1. Sélectionner **[!UICONTROL Extensions]** dans le rail de gauche.

2. Sélectionner **[!UICONTROL Catalogue]** dans la barre supérieure.

3. Recherchez ou faites défiler jusqu’à l’extension SDK Web Adobe Experience Platform, puis sélectionnez **[!UICONTROL Installer]** pour l’installer.

   <img src="./assets/aepwebsdk-extension.png" width="35%"/>

4. Sélectionnez votre environnement de test et votre flux de données créé précédemment pour votre [!UICONTROL Environnement de production] et (facultatif) [!UICONTROL Environnement d’évaluation] et [!UICONTROL Environnement de développement].

   ![Configuration de l’extension SDK Web AEP](./assets/aepwebsk-extension-datastreams.png)

   Sélectionnez **[!UICONTROL Enregistrer]**.

Voir [Configuration de l’extension du SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) pour plus d’informations.

Vous souhaitez également configurer l’extension du service d’ID d’Experience Cloud afin que vous puissiez facilement utiliser le service d’ID d’Experience Cloud. Le service d’ID d’Experience Cloud identifie les visiteurs dans toutes les solutions Adobe Experience Cloud.

Pour créer et configurer l’extension du service d’ID Experience Cloud :

1. Sélectionner **[!UICONTROL Extensions]** dans le rail de gauche.

2. Sélectionner **[!UICONTROL Catalogue]** dans la barre supérieure.

3. Recherchez ou faites défiler l’écran jusqu’à l’extension Experience Cloud ID Service, puis sélectionnez **[!UICONTROL Installer]** pour l’installer.

   <img src="./assets/ecid-extension.png" width="35%"/>

4. Conservez toutes les configurations par défaut.

5. Sélectionnez **[!UICONTROL Enregistrer]**.

#### **Éléments de données**

Les éléments de données sont les blocs de construction de votre dictionnaire de données (ou mappage de données). Utilisez des éléments de données pour recueillir, organiser et diffuser des données dans les technologies marketing et publicitaires. Vous allez configurer des éléments de données dans votre balise qui lisent à partir de votre couche de données et qui peuvent être utilisés pour diffuser des données dans Adobe Experience Platform.

Il existe différents types d’éléments de données. Vous allez d’abord configurer un élément de données pour capturer le nom de page que les visiteurs consultent sur votre site.

Pour définir un élément de données de nom de page :

1. Sélectionner **[!UICONTROL Éléments de données]** dans le rail de gauche.

2. Sélectionner **[!UICONTROL Ajouter un élément de données]**.

3. Dans le [!UICONTROL Créer un élément de données] dialog :

   - Nommez votre élément de données, par exemple : `Page Name`.

   - Sélectionner **[!UICONTROL Core]** de la [!UICONTROL Extension] liste.

   - Sélectionner **[!UICONTROL Informations sur la page]** de la [!UICONTROL Type d’élément de données] liste.

   - Sélectionner **[!UICONTROL Titre]** de la [!UICONTROL Attribut] liste.

      ![Créer un élément de date à l’aide des informations sur la page](./assets/create-dataelement-1.png)

      Vous pouvez également avoir utilisé la valeur d’une variable de votre couche de données, par exemple `pageName` et le [!UICONTROL Variable JavaScript] type d’élément de données pour définir l’élément de données.

      ![Création d’un élément de données à l’aide de la variable JavaScript](./assets/create-dataelement-2.png)

   - Sélectionnez **[!UICONTROL Enregistrer]**.

Vous souhaitez maintenant configurer un élément de données référençant l’ID Experience Cloud automatiquement fourni par le SDK Web de Adobe Experience Platform et disponible via l’extension du service d’ID Experience Cloud.

Pour définir un élément de données ECID :

1. Sélectionner **[!UICONTROL Éléments de données]** dans le rail de gauche.

2. Sélectionner **[!UICONTROL Ajouter un élément de données]**.

3. Dans le [!UICONTROL Créer un élément de données] dialog :

   - Nommez votre élément de données, par exemple : `ECID`.

   - Sélectionner **[!UICONTROL Service d’ID Experience Cloud]** de la [!UICONTROL Extension] liste.

   - Sélectionner **[!UICONTROL ECID]** de la [!UICONTROL Type d’élément de données] liste.

      ![Élément de données ECID](./assets/ecid-dataelement.png)

   - Sélectionnez **[!UICONTROL Enregistrer]**.

Enfin, vous souhaitez maintenant mapper l’un de vos éléments de données spécifiques au schéma que vous avez défini précédemment. Vous devez définir un autre élément de données qui fournit une représentation de votre schéma XDM.

Pour définir un élément de données d’objet XDM :

1. Sélectionner **[!UICONTROL Éléments de données]** dans le rail de gauche.

2. Sélectionner **[!UICONTROL Ajouter un élément de données]**.

3. Dans le [!UICONTROL Créer un élément de données] dialog :

   - Nommez votre élément de données, par exemple : `XDM - Page View`.

   - Sélectionner **[!UICONTROL SDK Web Adobe Experience Platform]** de la [!UICONTROL Extension] liste.

   - Sélectionner **[!UICONTROL Objet XDM]** de la [!UICONTROL Type d’élément de données] liste.

   - Sélectionnez votre environnement de test dans la [!UICONTROL Sandbox] liste.

   - Sélectionnez votre schéma dans le [!UICONTROL Schéma] liste.

   - Faites correspondre la variable `identification > core > ecid` , défini dans votre schéma, sur l’élément de données ECID. Sélectionnez l’icône du lecteur pour sélectionner facilement l’élément de données ECID dans votre liste d’éléments de données.

      ![Sélectionner un élément de données ECID](./assets/pick-ecid-dataelement.png)

      ![Mapper l’élément de données ECID](./assets/map-ecid.png)


   - Faites correspondre la variable `web > webPageDetails > name` , défini dans votre schéma, sur l’élément de données Nom de page .

      ![Elément de données Nom de page de carte](./assets/map-pagename.png)

   - Sélectionnez **[!UICONTROL Enregistrer]**.


#### **Règles**

Dans Adobe Experience Platform, les balises obéissent à un système basé sur des règles. Elles recherchent les interactions utilisateur et les données associées. Lorsque les critères définis dans votre règle sont satisfaits, la règle déclenche l’extension, le script ou le code côté client que vous avez identifié. Vous pouvez utiliser des règles pour envoyer des données (comme un objet XDM) dans Adobe Experience Platform à l’aide de l’extension SDK Web Adobe Experience Platform.

Pour définir une règle :

1. Sélectionner **[!UICONTROL Règles]** dans le rail de gauche.

2. Sélectionner **[!UICONTROL Créer une règle]**.

3. Dans le [!UICONTROL Créer une règle] dialog :

   - Nommez la règle, par exemple : `Page View`.

   - Sélectionner **[!UICONTROL + Ajouter]** underneath [!UICONTROL Événements].

   - Dans le [!UICONTROL Configuration d’événement] dialog :

      - Sélectionner **[!UICONTROL Core]** de la [!UICONTROL Extension] liste.

      - Sélectionner **[!UICONTROL Fenêtre chargée]** de la [!UICONTROL Type d’événement] liste.

         ![Règle - Configuration d’événement](./assets/event-windowloaded-pageview.png)

      - Sélectionnez **[!UICONTROL Conserver les modifications]**.
   - Sélectionner **[!UICONTROL + Ajouter]** underneath [!UICONTROL Actions].

   - Dans le [!UICONTROL Configuration d’action] dialog :

      - Sélectionner **[!UICONTROL SDK Web Adobe Experience Platform]** de la [!UICONTROL Extension] liste.

      - Sélectionner **[!UICONTROL Envoyer un événement]** de la [!UICONTROL Type d’action] liste.

      - Sélectionner **[!UICONTROL web.webpagedetails.pageViews]** de la [!UICONTROL Type] liste.

      - Cliquez sur l’icône de l’accélérateur en regard de  [!UICONTROL Données XDM] et sélectionnez **[!UICONTROL XDM - Page vue]** dans la liste des éléments de données.

         ![Règle - Configuration de l’action](./assets/action-pageview-xdm.png)

      - Sélectionnez **[!UICONTROL Conserver les modifications]**.
   - Votre règle doit se présenter comme suit :

      ![Créer une règle](assets/rule-pageview.png)

   - Sélectionnez **[!UICONTROL Enregistrer]**.





Il s’agit simplement d’un exemple de définition d’une règle qui envoie des données XDM, contenant des valeurs d’autres éléments de données, à Adobe Experience Platform.

Vous pouvez utiliser des règles de différentes manières dans votre balise pour manipuler des variables (en utilisant vos éléments de données).

Voir [Règles](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=fr) pour plus d’informations.

### Créer et publier votre balise

Après avoir défini des éléments de données et des règles, vous devez créer et publier votre balise. Lorsque vous créez une version de bibliothèque, vous devez l’affecter à un environnement. Les extensions, règles et éléments de données de la version sont ensuite compilés et placés dans l’environnement attribué. Chaque environnement fournit un code incorporé unique qui vous permet d’intégrer la version qui lui est assignée dans votre site.

Pour créer et publier votre balise :

1. Sélectionner **[!UICONTROL Flux de publication]** dans le rail de gauche.

2. Sélectionner **[!UICONTROL Sélectionner une bibliothèque de travail]**, suivie de **[!UICONTROL Ajouter une bibliothèque...]**.

3. Dans le [!UICONTROL Créer une bibliothèque] dialog :

   - Donnez un nom à la bibliothèque.

   - Sélectionner **[!UICONTROL Développement (développement)]** de la [!UICONTROL Environnement] liste.

   - Sélectionner **[!UICONTROL + Ajouter toutes les ressources modifiées]**.

      ![Publier - Créer une bibliothèque](./assets/create-library-aep.png)

   - Sélectionner **[!UICONTROL Enregistrement et création pour le développement]**.

   Cela permet d’enregistrer et de créer la balise pour votre environnement de développement. Un point vert indique que votre balise a été créée avec succès dans votre environnement de développement.

4. Vous pouvez sélectionner **[!UICONTROL ...]** pour recréer la bibliothèque ou la déplacer vers un environnement d’évaluation ou de production.

   ![Publier - Créer la bibliothèque](./assets/build-library.png)

Les balises Adobe Experience Platform prennent en charge les processus de publication simples à complexes qui doivent répondre à votre déploiement du SDK Web de Adobe Experience Platform.

Voir [Présentation de la publication](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) pour plus d’informations.


### Récupération du code de balise

Enfin, vous devez installer votre balise sur le site Web dont vous souhaitez effectuer le suivi. Cela implique de placer le code dans la balise d’en-tête du modèle de votre site web.

Pour obtenir le code qui référence votre balise :

1. Sélectionner **[!UICONTROL Environnements]** dans le rail de gauche.

2. Dans la liste des environnements, sélectionnez le bouton d’installation (case) approprié.

   Dans le [!UICONTROL Instructions d’installation Web] , sélectionnez le bouton Copier en regard du code de script qui doit se présenter comme suit :

   ```javascript
   <script src="https://assets.adobedtm.com/2a518741ab24/806645a0b9bb/launch-716db315b4e2-development.min.js" async></script>
   ```

   ![Environnement](./assets/environment.png)

3. Sélectionner **[!UICONTROL Fermer]**.

Au lieu du code de l’environnement de développement, vous avez peut-être sélectionné un autre environnement (d’évaluation et de production) en fonction de l’emplacement où vous déployez le SDK Web de Adobe Experience Platform.

Voir [Environnements](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=fr?) pour plus d’informations.

## Déploiement et validation

Vous pouvez désormais déployer le code sur la version de développement de votre site web au sein du `<head>` balise . Une fois déployé, votre site web commence à collecter des données dans Adobe Experience Platform.

Validez votre mise en oeuvre, corrigez-la si nécessaire, puis déployez-la dans votre environnement d’évaluation et de production à l’aide de la fonctionnalité de workflow de publication des balises.

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

   - Sélectionnez le jeu de données que vous avez créé précédemment (`Example dataset`) et tout autre jeu de données que vous souhaitez inclure dans votre connexion.

      ![Ajouter des jeux de données](./assets/cja-connections-2b.png)

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
>Vous avez terminé toutes les étapes. En commençant par définir les données que vous souhaitez collecter (schéma) et l’emplacement de stockage (jeu de données) dans Adobe Experience Platform, vous avez configuré un flux de données sur le réseau Edge pour vous assurer que les données peuvent être transférées vers ce jeu de données. Vous avez ensuite défini et déployé votre balise contenant les extensions (SDK web Adobe Experience Platform, service d’ID Experience Cloud), les éléments de données et les règles pour capturer les données de votre site web et envoyer ces données à votre flux de données. Vous avez défini une connexion dans Customer Journey Analytics afin d’utiliser les données de suivi de votre site web et d’autres données. Votre définition de vue de données vous a permis de spécifier la dimension et les mesures à utiliser. Vous avez enfin créé votre premier projet qui visualise et analyse vos données.
