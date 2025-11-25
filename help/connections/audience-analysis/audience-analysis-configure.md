---
title: Configuration de l’analyse de l’audience
description: Découvrez comment configurer l’analyse de l’audience
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3f4b9e5929f1fe5bf0524236ab956487469c1778
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 13%

---

# Configuration de l’analyse de l’audience {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="Politique de fusion"
>abstract="Les politiques de fusion combinent les données de profil de plusieurs jeux de données en profils clients unifiés utilisés pour la création d’audiences. Sélectionnez « Basé sur le temps par défaut » si plusieurs politiques de fusion s’affichent et que vous ne savez pas laquelle choisir. Vous pouvez également consulter votre équipe de données pour savoir quelles audiences sont associées à chaque politique de fusion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="Sandbox"
>abstract="Sélectionnez le sandbox qui contient les jeux de données de profil Experience Platform corrects. Ces jeux de données doivent contenir les données d’audience pour lesquelles vous souhaitez créer des rapports dans Analysis Workspace. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="ID de personne"
>abstract="Sélectionnez un champ dans le schéma qui représente l’ID de personne. La sélection est limitée à la liste des champs du schéma qui sont marqués comme Identité et qui possèdent un espace de noms d’identité."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="Utiliser l’espace de noms d’identité principal"
>abstract="Activez cette option si vous souhaitez que Customer Journey Analytics recherche l’identité dans le mappage d’identités marqué d’un attribut primary=true et utilise cette identité comme ID de personne pour cette ligne. Cette identité est la clé primaire utilisée dans Experience Platform pour le partitionnement. <br/>Si vous laissez cette option désactivée, sélectionnez un espace de noms dans le champ Espace de noms d’identité ci-dessous. Customer Journey Analytics recherche cette clé d’espace de noms dans le mappage d’identité de chaque ligne et utilise l’identité sous cet espace de noms comme ID de personne pour cette ligne."

<!-- markdownlint-enable MD034 -->

L’analyse de l’audience vous permet d’ingérer des données d’appartenance à une audience à partir de jeux de données Profil Experience Platform dans une connexion Customer Journey Analytics. Les audiences deviennent disponibles en tant que nouvelles dimensions à utiliser dans Analysis Workspace. Pour obtenir des informations d’aperçu plus détaillées sur l’analyse de l’audience, voir [Présentation de l’analyse des audiences](/help/connections/audience-analysis/audience-analysis-overview.md).

Lors de la création d’une configuration d’analyse d’audience, vous sélectionnez le sandbox et la politique de fusion associés aux audiences Experience Platform que vous souhaitez analyser. Customer Journey Analytics crée un jeu de données de recherche, puis ajoute automatiquement le jeu de données de recherche et le jeu de données de profil à la connexion que vous choisissez.

Pour créer une configuration d’analyse d’audience :

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Gestion des données]** > **[!UICONTROL Configuration de l’analyse de l’audience]**.

   ![Page principale de l’analyse de l’audience](assets/audience-analysis-empty.png)

1. Sélectionnez **[!UICONTROL Créer une configuration]**.

   ![Créer une configuration d’analyse d’audience](assets/audience-analysis-create.png)

1. Dans la section **[!UICONTROL Détails]**, spécifiez les informations suivantes :

   | Champ | Description |
   |---------|----------|
   | **[!UICONTROL Nom]** | Attribuez un nom à la configuration. |
   | **[!UICONTROL Sandbox]** | Sélectionnez la sandbox qui contient le jeu de données de profil que vous souhaitez ajouter à votre connexion. <p>Adobe Experience Platform fournit des [sandbox](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) qui divisent une instance de plateforme unique en environnements virtuels distincts pour favoriser le développement et l’évolution d’applications d’expérience digitale. Vous pouvez considérer les sandbox comme des « silos de données » contenant des jeux de données. Les sandbox permettent de contrôler l’accès aux jeux de données.</p> |

1. Dans la section **[!UICONTROL Jeu de données de profil]**, spécifiez les informations suivantes :

   | Champ | Description |
   |---------|----------|
   | **[!UICONTROL Politique de fusion]** | Sélectionnez la politique de fusion qui correspond au jeu de données de profil que vous souhaitez utiliser pour l’analyse de l’audience. <p>Les politiques de fusion déterminent la manière dont Adobe Experience Platform combine les données de profil de plusieurs jeux de données en profils clients unifiés utilisés pour la création d’audiences. La politique de fusion que vous sélectionnez affecte les attributs du profil inclus dans vos audiences. Chaque jour, un instantané de ces données est généré dans Experience Platform. Cet instantané fournit une vue statique des données à un moment spécifique dans le temps et n’inclut aucune donnée d’événement.</p><p>Sélectionnez la politique de fusion **[!UICONTROL Par défaut basée sur le temps]** si plusieurs politiques de fusion s’affichent et que vous ne savez pas laquelle choisir. Vous pouvez également consulter votre équipe de données pour mieux comprendre les audiences associées à chaque politique de fusion.</p> |
   | **[!UICONTROL Jeu de données du profil]** | Le jeu de données de profil associé à la politique de fusion que vous avez sélectionnée. Ce jeu de données de profil inclut les données d’audience Experience Platform que vous souhaitez analyser. Ce jeu de données de profil est ajouté à la connexion que vous sélectionnez.<p>Une fois que vous avez choisi une politique de fusion, l’exportation de l’instantané du profil s’affiche. Par exemple : `Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`.</p><p>Pour plus d’informations, voir [Jeux de données d’attributs de profil](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets) dans le guide des tableaux de bord d’Experience Platform.</p> |

1. Dans la section **[!UICONTROL Connexion]**, cliquez sur **[!UICONTROL Sélectionner une connexion]**.

1. Dans la boîte de dialogue Connexions, cochez la case en regard de la connexion à laquelle vous souhaitez ajouter le jeu de données de profil, puis sélectionnez **[!UICONTROL Utiliser la connexion]**.

1. Spécifiez les informations suivantes pour configurer la connexion :

   | Champ | Description |
   |---------|----------|
   | **[!UICONTROL ID de personne]** | Sélectionnez un champ dans le schéma qui représente l’ID de personne. La sélection est limitée à la liste des champs du schéma qui sont marqués comme Identité et qui possèdent un espace de noms d’identité.<p>Si aucun ID de personne n’est disponible, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Voir [Définir des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations.</p> |
   | **[!UICONTROL Utiliser l’espace de noms d’identité principal]** | Cette option s’affiche si vous sélectionnez **[!UICONTROL carte des identités]** pour l’ID de personne.<p>Activez cette option si vous souhaitez que Customer Journey Analytics recherche l’identité dans le mappage d’identités marqué d’un attribut primary=true et utilise cette identité comme ID de personne pour cette ligne. Cette identité est la clé primaire utilisée dans Experience Platform pour le partitionnement. Cette identité est également le candidat idéal pour une utilisation en tant qu’ID de personne Customer Journey Analytics (selon la configuration du jeu de données dans une connexion Customer Journey Analytics).</p> |
   | **[!UICONTROL Espace de noms d’identité]** | Cette option s’affiche si vous sélectionnez **[!UICONTROL carte des identités]** pour l’ID de personne. Cette option est désactivée si vous utilisez l’espace de noms d’identifiant de Principal. <p>Les espaces de noms d’identité sont un composant du [service d’identités d’Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/namespaces). Les espaces de noms servent d’indicateurs pour le contexte auquel une identité se rapporte. Si vous spécifiez un espace de noms, Customer Journey Analytics recherche cette clé d’espace de noms dans le mappage d’identités de chaque ligne et utilise l’identité sous cet espace de noms comme ID de personne pour cette ligne. Comme Customer Journey Analytics ne peut pas analyser complètement le jeu de données de toutes les lignes pour déterminer les espaces de noms présents, tous les espaces de noms possibles sont affichés dans le menu déroulant. Sachez quels espaces de noms sont spécifiés dans les données ; ces derniers ne sont pas détectés automatiquement.</p> |

1. Dans la section **[!UICONTROL Vues de données]**, cliquez sur **[!UICONTROL Sélectionner les vues de données]**.

1. Dans la boîte de dialogue Vues de données , cochez la case en regard d’une ou de plusieurs vues de données à utiliser lors de l’analyse des données d’audience Experience Platform dans Analysis Workspace. Ces vues de données sont automatiquement configurées avec les données d’audience Experience Platform pour la création de rapports.

1. Sélectionnez **[!UICONTROL Utiliser les vues de données]**.

1. Sélectionnez **[!UICONTROL Créer]** pour créer la configuration.

   Comme le jeu de données profil est mis à jour une fois par jour, les audiences sont disponibles dans les vues de données Customer Journey Analytics le lendemain de la création de la configuration de l’analyse de l’audience.


