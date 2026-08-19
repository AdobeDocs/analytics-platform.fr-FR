---
title: Créer un flux de données
description: Apprenez comment créer un flux de données et découvrez les informations sur les fichiers à fournir à Adobe.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e7c2598015d3ee271bb7e0f64937fd1c457b5433
workflow-type: tm+mt
source-wordcount: 4033
ht-degree: 20%

---

# Créer un flux de données

{{release-limited-testing}}

Lors de la création d’un flux de données, vous fournissez à Adobe les éléments suivants :

* Informations sur la destination vers laquelle envoyer les fichiers de données brutes

* Les données à inclure dans chaque fichier

* Fréquence d’envoi des données (y compris le délai de traitement pour la capture des événements d’arrivée tardive)

Avant de créer un flux de données, il est important de comprendre les bases des flux de données et de vous assurer que vous remplissez toutes les conditions préalables. Consultez la [vue d’ensemble des flux de données](data-feed-overview.md) pour en savoir plus.

## Créer et configurer un flux de données {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="Manifeste"
>abstract="Choisissez d’inclure un fichier manifeste avec chaque diffusion de flux de données. Les fichiers manifeste contiennent des informations pour chaque fichier inclus dans le flux de données. Lors de l’envoi de données de flux de données dans un seul package, vous pouvez également choisir d’inclure un fichier de fin, mais les fichiers de manifeste sont recommandés. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="Notifier les problèmes, lorsqu’ils sont terminés et lorsqu’ils arrivent à échéance."
>abstract="Indiquez une ou plusieurs adresses e-mail où une notification doit être envoyée lorsque le flux de données se termine, arrive à expiration ou rencontre des problèmes. Séparez plusieurs adresses e-mail par une virgule."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="Délai de traitement"
>abstract="Durée d’attente des événements arrivant en retard avant de traiter un fichier de flux de données. Tous les accès tardifs qui arrivent pendant la période de délai de traitement sont inclus dans le flux de données. <p>Les délais de traitement sont utiles pour diverses raisons, par exemple pour permettre aux implémentations mobiles de permettre aux appareils hors ligne de se connecter et d’envoyer des données, ou pour s’adapter aux processus côté serveur de votre entreprise dans la gestion des fichiers précédemment traités.</p><p>Pour être incluses, les sessions doivent commencer après la coupure du délai de traitement ; les sessions qui commencent avant la coupure et se terminent dans le délai de traitement ne sont pas incluses.</p><p>Customer Journey Analytics détermine de manière dynamique le délai optimal en fonction de la durée habituelle des événements arrivant en retard pour votre flux, mais vous pouvez le définir manuellement sur un délai de 2, 3, 4 ou 8 heures.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="Les données de l’agent utilisateur et les données de recherche de périphérique ne peuvent pas exister dans la même configuration de flux de données."

<!-- markdownlint-enable MD034 -->

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.

1. Sélectionnez [!UICONTROL **Customer Journey Analytics**] dans le sélecteur d’applications ![App](/help/assets/icons/Apps.svg) en haut à droite de l’interface.

1. Dans la barre de navigation supérieure, accédez à [!UICONTROL **Composants**] > [!UICONTROL **Exports**].

1. Sélectionnez l’onglet [!UICONTROL **Flux de données**].

1. Sélectionnez [!UICONTROL **Créer**] dans le coin supérieur droit de l’écran.

   Si aucun flux de données n’a été précédemment créé, sélectionnez [!UICONTROL **Créer un flux de données**] dans le tableau vide.

   Une page s’affiche avec les onglets suivants : [!UICONTROL **Détails**], [!UICONTROL **Structure des données**] et [!UICONTROL **Diffusion**].

   ![Nouvelle page de flux de données](assets/data-feed-new.png)

1. Dans l’onglet [!UICONTROL **Détails**], renseignez les champs suivants :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom**] | Nom du flux de données. Les noms doivent être uniques dans la vue de données sélectionnée et peuvent contenir jusqu’à 255 caractères. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Balises**] | Appliquez des balises au flux de données pour faciliter la catégorisation. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Description**] | Spécifiez une description pour le flux de données (500 caractères maximum). La description que vous ajoutez est visible lors de la modification du flux de données. |
   | [!UICONTROL **Vue de données**] | Sélectionnez la vue de données contenant les données à exporter.<p>Tenez compte des points suivants lors de la sélection d’une vue de données :</p> <ul><li>Si plusieurs flux de données sont créés pour la même vue de données, chaque flux de données doit avoir des définitions de colonne différentes.</li><li>La liste des colonnes disponibles dépend de la société de connexion à laquelle appartient la vue de données sélectionnée. Si vous modifiez la vue de données, la liste des colonnes disponibles peut changer. </li></ul> |

1. Sélectionnez [!UICONTROL **Suivant**].

1. Dans l’onglet [!UICONTROL **Structure de données**], assurez-vous que la vue de données appropriée est sélectionnée dans le champ **[!UICONTROL Vue de données]**.

   <!--add screenshot-->

1. Dans le menu déroulant [!UICONTROL **Segments**], recherchez et sélectionnez n’importe quel segment pour filtrer les données incluses dans votre flux.

   Lorsque vous appliquez plusieurs segments, ils sont associés à un opérateur AND. Pour joindre des segments avec un opérateur OR, vous devez d’abord créer un segment dans le créateur de segments, puis appliquer le nouveau segment au flux de données.

1. Ajoutez des composants à la configuration des flux de données. Le rail de gauche affiche uniquement les composants valides pour les flux de données.

   * **Glisser-déposer** : faites glisser des composants du rail de gauche vers la zone de travail. Maintenez la touche **[!UICONTROL Maj]** ou **[!UICONTROL Commande]** (macOS) ou **[!UICONTROL Ctrl]** (Windows) enfoncée pour sélectionner plusieurs composants et les faire glisser simultanément.
   * **Bouton Plus** : sélectionnez l’icône Plus ![Ajouter](/help/assets/icons/Add.svg) en regard de n’importe quel composant dans le rail de gauche pour l’ajouter à la zone de travail.
   * **[!UICONTROL Tout afficher]** : sélectionnez **[!UICONTROL Tout afficher]** au bas de la liste des composants pour ouvrir une boîte de dialogue affichant tous les composants disponibles. Cochez la case en regard de chaque composant à ajouter, puis sélectionnez **[!UICONTROL Ajouter la sélection]**. Lorsqu’un terme de recherche ou une balise de filtre est actif dans le rail de gauche, un bouton **[!UICONTROL Ajouter tout]** s’affiche également pour vous permettre d’ajouter tous les résultats filtrés en même temps.

   Lorsque vous ajoutez un composant qui appartient à un champ de tableau XDM (par exemple, un champ de proposition Adobe Journey Optimizer), il apparaît sur la zone de travail sous la forme d’un groupe imbriqué réductible plutôt que d’un élément plat. Le groupe reflète la structure de données sous-jacente et génère un tableau imbriqué dans le fichier exporté.

   <!--add screenshot-->

   +++ Dimensions toujours incluses dans les flux de données

   Les dimensions suivantes sont incluses par défaut dans chaque flux de données et ne peuvent pas être supprimées :

   | Nom de la dimension | Notes | Flux de données | Autres rapports |
   |---|---|---|---|
   | Date et heure UTC | Date et heure de l’événement, représentées dans le fuseau horaire UTC. Prend en charge la granularité inférieure à la seconde (micro-seconde). | Obligatoire | Non disponible |
   | ID de ligne | Identifiant unique pour chaque ligne incluse dans le flux de données. | Obligatoire | Non disponible |
   | Identifiant de session | Identifiant unique pour chaque session incluse dans le flux de données. | Obligatoire | Non disponible |
   | ID de personne | Identifiant de personne pour la vue de données et la connexion | Obligatoire | Norme facultative |
   | ID de compte {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Identifiant de compte lors de l’utilisation du conteneur Compte | Obligatoire | Norme facultative |

   +++

   +++ Dimensions qui ne peuvent pas être incluses dans les flux de données

   Les dimensions standard de Customer Journey Analytics ne peuvent pas être incluses dans les flux de données. Le tableau suivant répertorie ces dimensions :

   | Nom de la dimension | Notes | Flux de données |
   |---|---|---|
   | 5 minutes | Intervalles de cinq minutes lorsque des événements se sont produits (arrondi à l’unité inférieure) | Non disponible |
   | 15 minutes | Intervalles de quinze minutes lorsque des événements se sont produits (arrondi à l’unité inférieure) | Non disponible |
   | 30 minutes | Intervalles de trente minutes lorsque des événements se sont produits (arrondi à l’unité inférieure) | Non disponible |
   | Jour | Jour où un événement s’est produit | Non disponible |
   | Jour de la semaine | Jour de la semaine où un événement s’est produit | Non disponible |
   | Jour du mois | Jour du mois où un événement s’est produit | Non disponible |
   | Heure | Heure à laquelle l’événement s’est produit (arrondie à l’unité inférieure) | Non disponible |
   | Heure de la journée | Heure du jour où un événement s’est produit (arrondie à l’unité inférieure) | Non disponible |
   | Minute | Minute à laquelle un événement s’est produit (arrondi à l’unité inférieure) | Non disponible |
   | Minute de l’heure | Minute de l’heure à laquelle un événement s’est produit (arrondie à l’unité inférieure) | Non disponible |
   | Mois | Mois au cours duquel un événement s’est produit | Non disponible |
   | Mois de l’année | Mois de l’année au cours duquel un événement s’est produit | Non disponible |
   | Trimestre | Trimestre au cours duquel un événement s’est produit | Non disponible |
   | Trimestre de l’année | Trimestre de l’année au cours duquel un événement s’est produit | Non disponible |
   | Second | Deuxième occurrence (arrondi à l’unité inférieure) | Non disponible |
   | Semaine | Semaine au cours de laquelle un événement s’est produit | Non disponible |
   | Semaine de l’année | Semaine de l’année au cours de laquelle un événement s’est produit | Non disponible |
   | Année | Année au cours de laquelle un événement s’est produit | Non disponible |

   +++

   +++ Mesures qui ne peuvent pas être incluses dans les flux de données

   Les mesures standard Customer Journey Analytics suivantes ne peuvent pas être incluses dans les flux de données :

   | Nom de la mesure | Notes | Flux de données |
   |---|---|---|
   | Profil des visiteurs Adobe | | Non disponible |
   | Union des opportunités Adobe | | Non disponible |
   | Profil d’opportunités Adobe | | Non disponible |
   | Union des comptes Adobe | | Non disponible |
   | Profil des comptes Adobe | | Non disponible |
   | Union des groupes d’achat Adobe | | Non disponible |
   | Profil de groupes d’achats Adobe | | Non disponible |
   | Union des comptes globaux Adobe | | Non disponible |
   | Profil de comptes globaux Adobe | | Non disponible |
   | Union des personnes Adobe | | Non disponible |
   | Profil de personnes Adobe | | Non disponible |

   +++

   +++ Dimensions qui ne peuvent pas être utilisées ensemble dans les flux de données

   >[!IMPORTANT]
   >
   >Certaines dimensions ne peuvent pas être utilisées ensemble dans les jeux de données Experience Platform et ne peuvent donc pas être incluses dans le même flux de données.
   >
   >Si vous choisissez d’inclure les dimensions **Agent utilisateur** ou **ID mobile** dans votre flux de données, les dimensions répertoriées ci-dessous ne peuvent pas être ajoutées au flux de données.
   >
   >Si vous utilisez le SDK Web, cette restriction est appliquée dans les flux de données avant que les données n’arrivent dans un jeu de données Experience Platform. Pour plus d’informations, voir [Configurer la recherche d’appareil](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/configure#geolocation-device-lookup) dans [Créer et configurer des flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/configure) dans le guide Collecte de données .

   Les dimensions suivantes ne peuvent pas être utilisées avec les dimensions **Agent utilisateur** ou **ID mobile** :

   * Type de navigateur
   * Navigateur
   * Fabricant du dispositif portable
   * Type d’appareil mobile
   * Prise en charge de l&#39;audio sur le dispositif portable
   * DRM mobile
   * Java VM de mobile
   * Services d&#39;informations mobiles
   * Prise en charge des images sur le dispositif portable
   * Profondeur de couleur du dispositif portable
   * Protocoles Net mobile
   * Numéro d’appareil mobile
   * Mobile - Longueur max. d’adresse e-mail
   * Mobile - Décoration de courrier
   * Mobile - Presser pour parler
   * Largeur d’écran du périphérique mobile
   * Mobile - Longueur max. d’URL de navigateur
   * Système d’exploitation mobile (obsolète)
   * Hauteur d’écran du périphérique mobile
   * Prise en charge de la vidéo sur le dispositif portable
   * Prise en charge des cookies sur le dispositif portable
   * Mobile - Longueur max. du signet
   * Taille d’écran du périphérique mobile
   * Nom de l’appareil mobile
   * Types de systèmes d’exploitation
   * Systèmes d’exploitation

   +++

   +++ Mesures qui doivent être remplacées dans les flux de données

   Les mesures Customer Journey Analytics suivantes doivent être remplacées :

   | Nom de la mesure | Notes | Flux de données |
   |---|---|---|
   | Comptes [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | En fonction de l’identifiant de compte spécifié dans la connexion | Non disponible. Utilisez un nombre distinct de l’ID de compte. |
   | Groupe d&#39;achat {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Groupes d&#39;achat basés sur l&#39;ID de groupe d&#39;achat dans la connexion | Non disponible. Utiliser le nombre distinct de l&#39;ID du groupe d&#39;achat. |
   | Événements | Nombre de lignes de tous les jeux de données d’événements dans une connexion | Non disponible. Utilisez un nombre distinct de l’ID de ligne. |
   | Comptes globaux [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | En fonction de l’identifiant de comptes globaux dans la connexion | Non disponible. Utilisez un nombre distinct de l’identifiant de comptes globaux. |
   | Opportunités [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Opportunités basées sur l’ID d’opportunité dans la connexion | Non disponible. Utiliser le nombre distinct de l’ID d’opportunité. |
   | Personnes | En fonction de l’ID de personne spécifié dans une connexion | Non disponible. Utilisez un nombre distinct de l’ID de personne. |
   | Conversations | Nombre de conversations | Non disponible. Utilisez un nombre distinct de l’ID de conversation. |
   | Fins de session | Nombre d’événements qui étaient le dernier événement d’une session | Non disponible |
   | Débuts de session | Nombre d’événements qui ont été le premier événement d’une session | Non disponible |
   | Sessions | En fonction des paramètres de session de la vue de données | Non disponible. Utilisez un nombre distinct de l’ID de session. |
   | Durée (secondes) | Additionne le temps entre deux valeurs de dimension différentes | Non disponible |

   +++

   +++ Composants standard facultatifs

   | Nom du composant | Type | Notes | Flux de données |
   |---|---|---|---|
   | Matin/après-midi | Dimension de répartition temporelle | Matin ou après-midi | Non disponible |
   | ID de lot | Dimension | Identifiant d’un lot Experience Platform | Disponible |
   | Identifiant du jeu de données | Dimension | Identifiant d’un jeu de données Experience Platform | Disponible |
   | Jour du mois | Dimension de répartition temporelle | 1-31 | Non disponible |
   | Jour de la semaine | Dimension de répartition temporelle | Du lundi au dimanche | Non disponible |
   | Jour de l’année | Dimension de répartition temporelle | 1-366 | Non disponible |
   | Profondeur de l’événement | Dimension | Valeur numérique séquentielle (1, 2, 3, etc.) affecté à chaque interaction d’événement dans une session<p>Se réinitialise au début de chaque nouvelle session</p> | Disponible |
   | Heure de la journée | Dimension de répartition temporelle | 0-23 | Non disponible |
   | Mois de l’année | Dimension de répartition temporelle | Janvier-Décembre | Non disponible |
   | Premières sessions | Mesure | Première session définie par une personne dans la fenêtre de création de rapports | Non disponible |
   | Sessions récurrentes | Mesure | Sessions qui n’étaient pas la première session d’une personne | Non disponible |
   | Espace de noms de l’ID de personne | Dimension | Type d’ID dont est constitué l’ID de personne (par exemple, e-mail ou ID de cookie) | Disponible |
   | Identifiant de compte global {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Identifiant de compte global lors de l’utilisation du conteneur de compte global | Disponible |
   | ID de l’opportunité {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | ID de l’opportunité lors de l’utilisation du conteneur d’opportunités | Disponible |
   | ID de groupe d&#39;achat {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | ID groupe d&#39;achat lors de l&#39;utilisation du conteneur groupe d&#39;achat | Disponible |
   | Trimestre de l’année | Dimension de répartition temporelle | T1, T2, T3, T4 | Non disponible |
   | Session répétée | Mesure | Sessions qui n’ont pas été la toute première session d’une personne | Non disponible |
   | Type de session | Dimension | Deux valeurs : Première fois ou Récurrent | Non disponible |
   | Temps passé par événement | Dimension | Regroupe la mesure Durée de la visite dans des regroupements événement . | Non disponible |
   | Temps passé par session | Dimension | Regroupe la mesure Durée de la visite dans des regroupements de session | Non disponible |
   | Durée par personne | Dimension | Regroupe la mesure Temps passé dans des regroupements Personne . | Non disponible |
   | Week-end/Jour de semaine | Dimension de répartition temporelle | Week-end ou jour de la semaine | Non disponible |

   +++

1. (Facultatif) Réorganisez les composants sur la zone de travail en les faisant glisser. L’ordre que vous définissez est conservé dans l’ordre des colonnes du fichier de flux de données exporté.

1. (Facultatif) Modifiez l’ID de composant qui s’affiche dans la sortie du flux de données.

   1. Pointez sur un composant sur la zone de travail, puis sélectionnez l’icône d’informations.

   1. Dans le champ ID du composant , spécifiez un nouvel ID de composant.

      <!--add screenshot-->

1. (Facultatif) Utilisez les panneaux **[!UICONTROL Résumé du flux]** et **[!UICONTROL Aperçu du schéma]** sur le côté droit de la page pour passer en revue votre structure de données avant de continuer :

   * Le **[!UICONTROL résumé des flux]** affiche un nombre réel de composants, colonnes, dimensions et mesures que vous avez ajoutés.
   * L’**[!UICONTROL aperçu du schéma]** affiche une représentation JSON du schéma de flux de données qui se met à jour au fur et à mesure que vous ajoutez ou réorganisez des composants.
   * Le bouton **[!UICONTROL Exemples de lignes]** ouvre une boîte de dialogue qui affiche des exemples de lignes de sortie afin que vous puissiez vérifier que la structure semble correcte. Cette boîte de dialogue affiche uniquement des exemples de données et ne reflète pas vos données réelles.

   <!--add screenshot-->

1. Sous l’onglet [!UICONTROL **Diffusion**], dans la section [!UICONTROL **Planifier**], choisissez le type de flux que vous souhaitez créer (actif ou de renvoi), puis spécifiez la fenêtre de création de rapports, la fréquence et d’autres options de configuration :

   <!--add screenshot-->

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Type de flux**] | Sélectionnez le type de flux que vous souhaitez créer :<ul><li>[!UICONTROL **Flux en direct**] : exporte les données actuelles et futures.</li><li>[!UICONTROL **Flux de renvoi**] : exporte les données historiques. </li></ul> |
   | [!UICONTROL **Date de début**] | Date de début du flux de données. Pour les flux en direct, il doit s’agir d’aujourd’hui ou d’une date ultérieure. Pour les flux de renvoi, il doit s’agir d’une date passée dans la fenêtre de conservation des données de la vue de données. La date de début est basée sur le fuseau horaire de la vue de données. |
   | [!UICONTROL **Date d’expiration**] <br/>Disponible uniquement pour les flux en direct | Date à laquelle le flux de données expire et ne s’exécute plus. La date est basée sur le fuseau horaire de la vue de données. |
   | [!UICONTROL **Date de fin**]<br/> Disponible uniquement pour les flux de renvoi | Date de fin du flux de données. La date de fin ne peut pas être dans le futur. La date est basée sur le fuseau horaire de la vue de données. |
   | [!UICONTROL **Fréquence**] | Sélectionnez la fréquence d’envoi du flux de données. Les événements dont la date et l’heure se trouvent dans la fenêtre de fréquence sont inclus dans la diffusion du flux de données. Les champs [!UICONTROL **Période de recherche en amont**] et [!UICONTROL **Délai de traitement**] peuvent également affecter les événements inclus dans les données pour la fréquence de diffusion que vous choisissez.<p>Pour les flux en direct, sélectionnez cette option pour inclure l’équivalent d’une heure de données ou d’une journée de données. Pour les flux de renvoi, ce champ est verrouillé sur **Quotidien** et ne peut pas être modifié.</p><ul><li>**Quotidien** : les flux contiennent l’équivalent d’une journée complète de données, de minuit à minuit dans le fuseau horaire de la vue de données. <p>Cette option est obligatoire pour les flux de renvoi et facultative pour les flux en direct.</p></li><li>**Par heure** : les flux contiennent l’équivalent d’une heure de données. <p>Cette option est disponible uniquement pour les flux en direct.</p></li></ul> |
   | [!UICONTROL **Période de recherche en amont**] | Contrôle la période sur laquelle Customer Journey Analytics se base pour traiter la diffusion du flux de données. La valeur par défaut est de 30 jours. <p>La période de recherche en amont affecte la qualification du segment, le calcul de session, les transformations de champ dérivé et la persistance des dimensions. <p>Avant de configurer cette option, consultez les détails et les exemples décrits dans la section ci-dessous, [Comprendre la période de recherche en amont](#understand-the-lookback-date-range).</p> |
   | [!UICONTROL **Délai de traitement**] | Sélectionnez la durée d’attente avant de traiter un fichier de flux de données. La valeur par défaut est de 2 heures. Tous les événements arrivant tardivement pendant la période de retard du traitement sont inclus dans le flux de données. <p>Les délais de traitement sont utiles pour diverses raisons, par exemple pour permettre aux implémentations mobiles de permettre aux appareils hors ligne de se connecter et d’envoyer des données, ou pour s’adapter aux processus côté serveur de votre entreprise dans la gestion des fichiers précédemment traités. </p><p>Pour être incluses, les sessions doivent commencer après la coupure du délai de traitement ; les sessions qui commencent avant la coupure et se terminent dans le délai de traitement ne sont pas incluses.</p><p>Customer Journey Analytics détermine de manière dynamique le délai optimal en fonction de la durée habituelle des événements arrivant en retard pour votre flux, mais vous pouvez le définir manuellement sur un délai de 2, 3, 4 ou 8 heures.</p> |
   | [!UICONTROL **Format de compression**] | Sélectionnez le format de compression des fichiers de sortie Parquet diffusés vers votre destination cloud. Choisissez l’un des formats suivants :<ul><li>[!UICONTROL **Snappy**] : compression et décompression rapides avec des tailles de fichier modérées. Largement pris en charge par les plateformes de données modernes telles que BigQuery, Snowflake et Apache Spark.</li><li>[!UICONTROL **GZip**] : largement compatible, y compris avec les outils qui ne prennent pas en charge Snappy en mode natif. Recommandé si votre pipeline en aval nécessite une norme de compression largement reconnue.</li><li>[!UICONTROL **Z Standard (Zstd)**] : Efficacité de compression élevée avec décompression rapide. Convient si la réduction de la taille du fichier est une priorité et que vos outils prennent en charge Zstd.</li></ul> |

1. Sous l’onglet [!UICONTROL **Diffusion**], dans la section [!UICONTROL **Destination**], configurez la destination vers laquelle vous souhaitez envoyer les données.

   >[!NOTE]
   >
   >Tenez compte de ce qui suit lors de la configuration du rapport de destination :
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* Tous les comptes cloud que vous avez précédemment configurés peuvent être utilisés pour les flux de données. Vous pouvez configurer des comptes cloud à partir du gestionnaire d’emplacements dans [Composants > Exportations > Comptes d’emplacement](/help/components/exports/cloud-export-accounts.md).
   >
   >* Les comptes cloud sont associés à votre compte utilisateur Customer Journey Analytics. Les autres utilisateurs ne peuvent pas utiliser ni afficher les comptes cloud que vous configurez, sauf si vous les rendez disponibles pour tous les utilisateurs de votre organisation.
   >
   >* Vous pouvez modifier les emplacements que vous créez à partir du gestionnaire d’emplacements dans [Composants > Exportations > Emplacements](/help/components/exports/cloud-export-locations.md).

   Renseignez les champs suivants :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Afficher les destinations pour tous les utilisateurs**] | Si vous êtes un administrateur ou une administratrice système, vous pouvez activer cette option pour afficher les destinations créées par tous les utilisateurs et utilisatrices de votre organisation. Lorsque cette option est désactivée, seules les destinations que vous avez créées s’affichent. |
   | [!UICONTROL **Compte**] | Effectuez l’une des opérations suivantes :<ul><li>**Utiliser un compte existant :** sélectionnez le menu déroulant en regard du champ **[!UICONTROL Compte]**. Vous pouvez également commencer à saisir le nom du compte, puis le sélectionner dans le menu déroulant. <p>Vous ne pouvez accéder aux comptes que si vous les avez configurés ou s’ils sont partagés avec une organisation dont vous faites partie.</p></li><li>**Créer un compte :** sélectionnez **[!UICONTROL Ajouter un compte]** dans le menu **[!UICONTROL Compte]**. Pour plus d’informations sur la configuration du compte, voir [Configuration des comptes d’exportation dans le cloud](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Emplacement**] | Effectuez l’une des opérations suivantes :<ul><li>**Utiliser un emplacement existant :** sélectionnez le menu déroulant en regard du champ **[!UICONTROL Emplacement]**. Vous pouvez également commencer à saisir le nom de l’emplacement, puis le sélectionner dans le menu déroulant.</li><li>**Créer un emplacement :** sélectionnez **[!UICONTROL Ajouter un emplacement]** dans le menu **[!UICONTROL Emplacement]**. Pour plus d’informations sur la configuration de l’emplacement, voir [Configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Envoyer une notification par e-mail une fois l’opération terminée**] | Indiquez une ou plusieurs adresses e-mail auxquelles une notification doit être envoyée une fois le flux de données envoyé avec succès ou en cas d’échec. Plusieurs adresses e-mail doivent être séparées par une virgule. |
   | [!UICONTROL **Activer le manifeste**] | Choisissez d’inclure un fichier manifeste avec chaque diffusion de flux de données. Le fichier manifeste contient des informations pour chaque fichier inclus dans le flux de données. |

1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Comprendre la période de recherche en amont {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Période de recherche en amont"
>abstract="Contrôle l’historique de Customer Journey Analytics lors du traitement de chaque diffusion.<p>La fenêtre de fréquence (heure ou jour) détermine les événements inclus dans le flux de données, tandis que la **période de recherche en amont** fournit le contexte historique nécessaire pour classer correctement ces événements.</p><p>La qualification des segments, la persistance des dimensions, le calcul de session et les transformations de champs dérivés peuvent tous affecter les événements inclus.</p><p>Une recherche arrière plus longue améliore la précision ; une recherche arrière plus courte améliore les performances.</p>"

<!-- markdownlint-enable MD034 -->

La période de recherche en amont contrôle l’historique de Customer Journey Analytics lors du traitement de chaque diffusion de flux de données.

Les événements doivent toujours avoir des horodatages compris dans la fenêtre de fréquence (heure ou jour) pour être inclus dans la diffusion, mais les données qui se trouvent dans la **période de recherche en amont** fournissent le contexte historique nécessaire pour classer correctement ces événements.

Lors de la configuration de cette option, tenez compte des concepts importants suivants :

* Une période de recherche en amont plus longue permet généralement d’obtenir des données plus précises ; une période plus courte permet d’obtenir de meilleures performances de diffusion.
* La période de recherche en amont, ainsi que la fenêtre de fréquence, fonctionnent de la même manière que la période de création de rapports d’Analysis Workspace. Cependant, il existe [des différences majeures](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences). Ces différences peuvent entraîner des incohérences de données entre les rapports Workspace et les diffusions de flux de données.

La qualification des segments, le calcul des sessions, la persistance des dimensions et les transformations de champs dérivés sont chacun pris en compte lors du traitement des données dans la période de recherche en amont :

### Qualification de segment

Lorsqu’un segment est appliqué à votre définition de flux de données, les données comprises dans la période de recherche en amont déterminent les événements, sessions ou personnes qui remplissent les critères pour le segment. Le paramètre de conteneur du segment détermine la portée. (Les conteneurs possibles sont : Personne, Session ou Événement. Le B2B inclut les conteneurs supplémentaires suivants : compte global, compte, opportunité, groupe d’achat.)

>[!BEGINSHADEBOX]

**Exemple :**

Supposons que vous souhaitiez créer un flux de données pour comprendre le comportement des utilisateurs qui font partie d’une campagne marketing spécifique, la campagne B.

Pour ce faire, appliquez un segment au flux de données appelé _Utilisateurs dans la campagne B_, en indiquant que seuls les événements liés aux utilisateurs de ce segment doivent être inclus dans le flux de données.

Dans ce cas, les utilisateurs ne sont inclus dans le flux de données que s’ils remplissent **les deux** les conditions suivantes :

* L’utilisateur a eu un événement dont la date et l’heure se trouvent dans la fenêtre de fréquence du flux de données (l’heure ou le jour donné du flux de données).
* L’utilisateur s’est qualifié pour le segment _Campaign B_ **à un moment donné dans la période de recherche en amont**.

  Pour un événement de qualification qui s’est produit il y a 9 jours, cela signifie que l’utilisateur **serait inclus** dans le flux de données si la période de recherche en amont était définie sur 30 jours, mais que l’utilisateur **ne serait pas inclus** dans le flux de données si la période de recherche en amont était définie sur 7 jours.

>[!ENDSHADEBOX]

### Calcul de session

Les limites de session sont calculées à l’aide de données comprises dans la période de recherche en amont. <!--Maybe this matters more regarding what the session ID is? Could it impact the Session ID? This could impact several factors, such as session-based persistence.-->

### Persistance de Dimension

Lorsque vous définissez la persistance sur une dimension individuelle, vous définissez également une expiration pour déterminer la durée pendant laquelle l’élément de dimension persiste au-delà de l’événement sur lequel il est défini.

La période de recherche en amont affecte la persistance des dimensions lorsque l’expiration est définie sur l’une des options suivantes dans la vue de données :

* [!UICONTROL **Période de reporting des personnes**] : la période de recherche en amont devient la nouvelle période de reporting pour chaque dimension de la définition de flux de données qui utilise [!UICONTROL **Période de reporting des personnes**] comme expiration.
* [!UICONTROL **Heure personnalisée**] : si l’heure personnalisée sélectionnée s’étend au-delà de la période de recherche arrière, l’heure personnalisée est ignorée et la période de recherche arrière est utilisée pour l’expiration de la dimension pour chaque dimension de la définition du flux de données qui utilise [!UICONTROL **Heure personnalisée**] comme expiration. Les valeurs antérieures à la période de recherche en amont ne sont pas prises en compte.

  Pour plus d’informations sur la définition de la persistance sur les dimensions dans la vue de données, voir [Paramètres des composants de persistance](/help/data-views/component-settings/persistence.md).

Pour obtenir les données les plus précises possible, pensez à définir la période de recherche en amont sur une valeur égale ou supérieure à la persistance définie sur les dimensions dans vos données. Toutefois, gardez à l’esprit qu’une période de recherche en amont plus courte entraîne de meilleures performances pour les diffusions de flux de données.

>[!BEGINSHADEBOX]

**Exemple :**

Supposons que dans votre flux de données vous souhaitiez savoir quelle campagne marketing les utilisateurs ont vue à l’origine avant d’accéder à votre site.

Pour ce faire, définissez la persistance sur la dimension Campagnes avec l’Original comme modèle d’affectation.

Dans ce cas, la campagne d’origine s’affiche dans la sortie du flux de données uniquement si les utilisateurs et utilisatrices remplissent **les deux** les conditions suivantes :

* L’utilisateur a eu un événement dont la date et l’heure se trouvent dans la fenêtre de fréquence du flux de données (l’heure ou le jour donné du flux de données).

* L’utilisateur s’est qualifié pour la campagne d’origine **à un moment dans la période de recherche en amont**.

  Si l’utilisateur s’est qualifié pour la campagne d’origine il y a 9 jours, la campagne d’origine **est incluse** dans le flux de données si la période de recherche arrière est définie sur 30 jours, mais la campagne d’origine **n’est pas incluse** dans le flux de données si la période de recherche arrière est définie sur 7 jours.

>[!ENDSHADEBOX]

### Transformations de champ dérivées

Toutes les fonctions de champ dérivé qui font référence à des conteneurs utilisent la période de recherche en amont dans les exportations de flux de données. Quelles sont les fonctionnalités de date disponibles dans les champs dérivés ? <!--Not sure how this applies.-->



