---
title: Création et publication d’audiences dans Real-time Customer Profile
description: Découvrez comment publier des audiences à partir de Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 31381cd397a821cc3ff1b3c15ae968a7260a6e9e
workflow-type: tm+mt
source-wordcount: '1726'
ht-degree: 49%

---

# Créer et publier des audiences {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_audiences_refreshfrequency"
>title="Fréquence d’actualisation"
>abstract="déterminer la fréquence à laquelle l’appartenance d’une audience sera réévaluée ;<br/>Une fois les audiences ne sont évaluées qu’une seule fois."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_audiences_audiencelimit"
>title="Limite d’audience"
>abstract="L’actualisation des audiences est limitée en fonction de leur fréquence."

<!-- markdownlint-enable MD034 -->

Cette rubrique explique comment créer et publier des audiences identifiées en Customer Journey Analytics dans [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) dans Adobe Experience Platform pour le ciblage et la personnalisation des clients.

Lisez cet [aperçu](/help/components/audiences/audiences-overview.md) pour vous familiariser avec le concept d’audiences Customer Journey Analytics.

## Création et publication d’une audience {#create}

1. Pour commencer à créer et publier une audience, effectuez l’une des opérations suivantes :

   | Méthode de création | Détails |
   | --- | --- |
   | À partir du menu **[!UICONTROL Composants] > [!UICONTROL Audiences]** | La page du gestionnaire d’audiences s’ouvre. Cliquez sur **[!UICONTROL Créer une audience]** et le [!UICONTROL créateur d’audiences] s’ouvre. |
   | Dans un tableau à structure libre | Cliquez avec le bouton droit de la souris sur un élément d’une table à structure libre et sélectionnez **[!UICONTROL Créer une audience d’après la sélection]**. L’utilisation de cette méthode préremplit le filtre avec la dimension ou l’élément de dimension que vous avez sélectionné dans le tableau. |
   | À partir de l’interface utilisateur de création/modification de filtre | Cochez la case qui indique : **[!UICONTROL Créer une audience à partir de ce filtre]**. L’utilisation de cette méthode préremplit le filtre. |

   {style="table-layout:auto"}

   <!-- add beneath the Freeform table row above: | From within a Journey canvas visualization | Right-click a node in a Journey canvas visualization and select **[!UICONTROL Create audience]**. Using this method pre-populates the filter with the dimension or dimension item you selected in the table. | -->

1. Créez l’audience.

   Configurez ces paramètres avant de pouvoir publier l’audience.

   ![Capture d&#39;écran de la création d&#39;un paramètre d&#39;expansion de l&#39;audience décrite dans la section suivante.](assets/create-audience.png)

   | Paramètre | Description |
   | --- | --- |
   | [!UICONTROL Nom] | Nom de l’audience. |
   | [!UICONTROL Balises] | Toutes les balises que vous souhaitez affecter à l’audience à des fins d’organisation. Vous pouvez utiliser une balise préexistante ou en saisir une nouvelle. |
   | [!UICONTROL Description] | Ajoutez une bonne description de l’audience pour la différencier des autres. |
   | [!UICONTROL Fréquence d’actualisation] | Fréquence à laquelle vous souhaitez actualiser l’audience.<ul><li>Vous pouvez choisir de créer une audience unique (par défaut) qui ne doit pas être actualisée. Par exemple, cela peut s’avérer utile pour des campagnes ponctuelles spécifiques.</li><li>Vous pouvez sélectionner d’autres intervalles d’actualisation. Pour la fréquence d’actualisation de 4 heures, il existe une limite de 75 à 150 actualisations d’audience, selon vos droits Customer Journey Analytics.</li></ul> |
   | Date d’expiration | Lorsque l’audience cessera de s’actualiser. La valeur par défaut est d’un an à compter de la date de création. Les audiences arrivant à expiration sont traitées de la même manière que les rapports planifiés arrivant à expiration : l’administrateur reçoit un e-mail un mois avant l’expiration de l’audience. |
   | Actualiser l’intervalle de recherche en amont | Indique jusqu’à combien de temps en arrière vous souhaitez remonter dans votre fenêtre de données lors de la création de cette audience. La valeur maximale est de 90 jours. |
   | [!UICONTROL Période pour audience unique] | Période à laquelle vous souhaitez que l’audience unique soit publiée. |
   | [!UICONTROL Filtrer] | Les filtres sont la principale entrée de l’audience. Vous pouvez ajouter jusquʼà 20 filtres. Ces filtres peuvent être joints à l’aide des opérateurs `And` ou `Or`. |
   | [!UICONTROL Afficher les identifiants d’échantillon] | Des identifiants d’échantillon dans cette audience. Utilisez la barre de recherche pour rechercher des ID d’échantillons. |

   {style="table-layout:auto"}

1. Interpréter l’aperçu des données.

   L’aperçu de l’audience s’affiche dans le panneau de droite. Il permet une analyse résumée de l’audience que vous avez créée.

   ![Capture d&#39;écran de l&#39;aperçu des données présentant une analyse résumée de l&#39;audience.](assets/data-preview.png)

   | Paramètre d’aperçu | Description |
   | --- | --- |
   | Fenêtre [!UICONTROL Aperçu des données] | La période de l’audience. |
   | [!UICONTROL Total personnes] | Résumé du nombre total de personnes dans cette audience. Il peut atteindre 20 millions de personnes. Si votre audience dépasse 20 millions de personnes, vous devez réduire la taille de l’audience avant de pouvoir la publier. |
   | [!UICONTROL Limite de taille d’audience] | Indique à quel point cette audience est éloignée de la limite de 20 millions. |
   | [!UICONTROL Retour dʼaudience estimé] | Ce paramètre est utile pour recibler les clients de cette audience qui reviennent sur votre site, application mobile ou autre canal (en d’autres termes, qui sont de nouveau affichés dans ce jeu de données). <p>Ici, vous pouvez sélectionner la période (les 7 prochains jours, les 2 prochaines semaines, le mois prochain) pour l’estimation du nombre de clients susceptibles de revenir. |
   | [!UICONTROL Retour estimé] | Ce nombre vous donne une estimation du nombre de clients récurrents sur la période que vous avez sélectionnée dans la liste déroulante. Nous regardons le taux de perte historique pour cette audience afin de prédire ce nombre. |
   | [!UICONTROL Prévisualiser les mesures] | Ce paramètre vous permet de consulter des mesures spécifiques pour déterminer si l’audience contribue à un montant disproportionné à cette mesure, par exemple : ‘[!UICONTROL Recettes]’ ou ‘[!UICONTROL Temps moyen passé sur le site]’. Il vous donne le nombre agrégé de la mesure, ainsi que le pourcentage du total qu’il représente. Vous pouvez sélectionner n’importe quelle mesure disponible dans votre vue de données. |
   | [!UICONTROL Espaces de noms inclus] | Espaces de noms spécifiques associés aux personnes de votre audience. Par exemple, ECID, identifiant CRM, adresses électroniques, etc. |
   | [!UICONTROL Sandbox] | La [sandbox Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr) dans laquelle réside cette audience. Lorsque vous publiez cette audience sur Platform, vous ne pouvez l’utiliser que dans les limites de cette sandbox. |

   {style="table-layout:auto"}

1. Vérifiez deux fois la configuration de votre audience et cliquez sur **[!UICONTROL Publier]**.

   Si tout s’est bien passé, vous recevrez un message de confirmation annonçant que l’audience a été publiée. Il suffit d’une minute ou deux pour que cette audience s’affiche dans Experience Platform. (Même pour les audiences avec des millions de membres, cela devrait prendre moins de 5 minutes.)

1. Cliquez sur **[!UICONTROL Afficher l’audience dans AEP]** dans le même message et vous serez dirigé vers la fonction [Interface utilisateur des segments](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=fr) dans Adobe Experience Platform. Plus d’informations ci-dessous.

## Que se passe-t-il une fois qu’une audience est créée et publiée ? {#after-audience-created}

Une fois que vous avez créé et publié une audience dans Customer Journey Analytics, celle-ci est disponible dans Experience Platform. Un segment de diffusion en continu Adobe Experience Platform ne sera créé que si votre entreprise est configurée pour la segmentation en continu.

* L’audience dans Platform partage le même nom/la même description que l’audience du Customer Journey Analytics, mais le nom sera ajouté avec l’ID de l’audience du Customer Journey Analytics pour s’assurer qu’il est unique.
* Toute modification apportée au nom ou à la description de l’audience dans Customer Journey Analytics est répercutée dans Platform.
* Si une audience est supprimée en Customer Journey Analytics, elle reste disponible dans Platform.

## Considérations relatives à la latence {#latency}

À plusieurs moments avant, pendant et après la publication de l’audience, des latences peuvent se produire. Voici un aperçu des latences possibles.

![Latences dans la publication d’audience comme décrit dans cette section.](assets/latency-diagram.svg)

| # | Point de latence | Durée de latence |
| --- | --- | --- |
| Non affiché | Connecteur source Adobe Analytics vers Analytics (A4T) | Jusqu’à 30 minutes |
| 1 | Ingestion de données dans le lac de données (à partir du connecteur source Analytics ou d’autres sources) | Jusqu’à 90 minutes |
| 2 | Ingestion de données du lac de données Experience Platform dans Customer Journey Analytics | Jusqu’à 90 minutes |
| 3 | Publication d’audiences dans Real-time Customer Profile, y compris la création automatique du segment de diffusion en continu et la possibilité pour le segment d’être prêt à recevoir les données. | Quelques secondes |
| 4 | Fréquence d’actualisation des audiences | <ul><li>Actualisation ponctuelle (latence inférieure à 5 minutes)</li><li>Actualiser toutes les 4 heures, tous les jours, toutes les semaines, tous les mois (la latence va de pair avec le taux d’actualisation) |
| 5 | Création de la destination dans Adobe Experience Platform : activation du nouveau segment | 1-2 heures |

{style="table-layout:auto"}

## Utilisation des audiences Customer Journey Analytics dans Experience Platform {#audiences-aep}

Customer Journey Analytics récupère toutes les combinaisons d’espace de noms et d’identifiants de l’audience publiée et les diffuse dans Real-Time Customer Profile (RTCP). Customer Journey Analytics envoie l’audience à l’Experience Platform avec le jeu d’identités principal, en fonction de ce qui a été sélectionné en tant que [!UICONTROL  ID de personne] lors de la configuration de la connexion.

Le RTCP examine ensuite chaque combinaison espace de noms/ID et recherche un profil dont il peut faire partie. Un profil est essentiellement un groupe d’espaces de noms, d’identifiants et d’appareils liés. S’il trouve un profil, il ajoute l’espace de noms et l’identifiant aux autres identifiants de ce profil en tant qu’attribut d’adhésion au segment. Par exemple, <user@adobe.com> peut être ciblé sur tous les appareils et canaux. Si aucun profil n’est trouvé, un nouveau profil est créé.

Pour afficher les audiences de Customer Journey Analytics dans Platform :

>[!AVAILABILITY]
>
>Les fonctionnalités décrites dans les étapes suivantes se trouvent dans la phase Tests limités de la version et peuvent ne pas être encore disponibles dans votre environnement. Si ces étapes ne correspondent pas à ce que vous voyez dans votre environnement, utilisez plutôt les étapes suivantes : Accédez à [!UICONTROL **Segments**] > [!UICONTROL **Créer des segments**] > [!UICONTROL **Onglet Audiences**] > [!UICONTROL **Audiences CJA**].
>
>Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour du Customer Journey Analytics, voir [Versions des fonctionnalités du Customer Journey Analytics](/help/release-notes/releases.md).

1. Développez [!UICONTROL **Client**] dans le panneau de gauche, puis sélectionnez [!UICONTROL **Audiences**]. <!-- is there a folder called "Customer Journey Analytics? -->

1. Sélectionnez l&#39;onglet [!UICONTROL **Parcourir**] .

   ![Option Audiences dans le panneau de gauche](assets/audiences-aep.png)

1. Pour localiser l’audience que vous avez publiée à partir de Customer Journey Analytics, effectuez l’une des opérations suivantes :

   * Triez le tableau en fonction de la colonne [!UICONTROL **Origin**] pour afficher les audiences qui présentent [!UICONTROL **Customer Journey Analytics**] comme origine.

   * Sélectionnez l’icône de filtre.

   * Utilisez le champ de recherche.

Pour plus d’informations sur l’utilisation des audiences dans Platform, reportez-vous à la section [Audiences](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#audiences) du [guide de l’interface utilisateur du créateur de segments](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=fr) dans la documentation de l’Experience Platform.


## Questions fréquentes {#faq}

Questions fréquentes sur la publication d’audiences.

+++**Que se passe-t-il si un utilisateur n’est plus membre d’une audience en Customer Journey Analytics ?**

Dans ce cas, un événement de sortie est envoyé à l’Experience Platform depuis Customer Journey Analytics.

+++

+++**Que se passe-t-il si vous supprimez une audience en Customer Journey Analytics ?**

Lorsqu’une audience Customer Journey Analytics est supprimée, elle ne s’affiche plus dans l’interface utilisateur Experience Platform. Cependant, aucun profil associé à cette audience n’est supprimé dans Platform.

+++

+++**Si un profil correspondant n’existe pas dans RTCDP, un nouveau profil sera-t-il créé ?**

Oui.

+++

+++**Customer Journey Analytics envoie-t-il les données d’audience sous forme d’événements de pipeline ou de fichier plat qui va également au lac de données ?**

Customer Journey Analytics diffuse les données dans RTCP par pipeline, et ces données sont également collectées dans un jeu de données système dans le lac de données.

+++

+++**Quelles identités Customer Journey Analytics envoie-t-il ?**

Les paires identité/espace de noms qui ont été spécifiées dans la [configuration de la connexion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection). Plus précisément, l’étape à laquelle un utilisateur ou une utilisatrice sélectionne le champ qu’il ou elle souhaite utiliser comme « ID de personne ».

+++

+++**Quel ID est choisi comme identité principale ?**

Voir ci-dessus. Nous n&#39;envoyons qu&#39;une seule identité par &quot;personne&quot; Customer Journey Analytics.

+++

+++**Le RTCP traite-t-il également les messages du Customer Journey Analytics ? Customer Journey Analytics peut-il ajouter des identités à un graphique d’identités de profil par le biais du partage d’audience ?**

Non. Nous n’envoyons qu’une seule identité par « personne », ainsi le RTCP ne consomme aucune périphérie de graphique.

+++

+++**À quelle heure des actualisations quotidiennes, hebdomadaires et mensuelles ont-elles lieu ? Quel jour de la semaine des actualisations hebdomadaires ont-elles lieu ?**

Le moment de l’actualisation est basé sur le moment où l’audience d’origine a été publiée et s’ancre à cette heure de la journée (et du jour de la semaine ou du mois).

+++

+++**L’heure d’actualisation quotidienne, hebdomadaire et mensuelle peut-elle être configurée par les utilisateurs ?**

Non, ils ne peuvent pas être configurés par les utilisateurs.

+++


## Étapes suivantes

* Pour gérer cette audience, accédez à l’[interface utilisateur de gestion](/help/components/audiences/manage.md).
