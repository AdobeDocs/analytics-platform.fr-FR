---
title: Créer un flux de données
description: Apprenez comment créer un flux de données et découvrez les informations sur les fichiers à fournir à Adobe.
hide: true
feature: Components
source-git-commit: 67ff091df786bc41809669ca2e5e6f4a912dbb33
workflow-type: tm+mt
source-wordcount: '2458'
ht-degree: 29%

---

# Créer un flux de données

Lors de la création d’un flux de données, vous fournissez à Adobe les éléments suivants :

* Informations sur la destination vers laquelle envoyer les fichiers de données brutes

* Les données à inclure dans chaque fichier

* La fréquence d’envoi du flux de données (y compris le délai de traitement pour capturer les accès en retard)

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
>title="Avertir une fois l’opération terminée"
>abstract="Indiquez une ou plusieurs adresses e-mail auxquelles une notification doit être envoyée après l’envoi du flux de données. Plusieurs adresses e-mail doivent être séparées par une virgule."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Période de recherche en amont"
>abstract="Contrôle le retour en arrière de Customer Journey Analytics lors du traitement de la diffusion du flux de données.<br/>Ce paramètre ne modifie pas la fenêtre de fréquence (heure ou jour). Toutefois, la période de recherche en amont peut influencer les données diffusées. La qualification du segment, le calcul de session, certaines transformations de champ dérivées et la persistance de dimension sont tous affectés par la période de recherche en amont."

<!-- markdownlint-enable MD034 -->

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.

1. Sélectionnez [!UICONTROL **Customer Journey Analytics**] dans le sélecteur d’applications ![App](/help/assets/icons/Apps.svg) en haut à droite de l’interface.

1. Dans la barre de navigation supérieure, accédez à [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Sélectionnez [!UICONTROL **Créer un flux de données**].

   Une page s’affiche avec les onglets suivants : [!UICONTROL **Détails**], [!UICONTROL **Structure des données**] et [!UICONTROL **Diffusion**].

   ![Nouvelle page de flux de données](assets/data-feed-new.png)

1. Dans la section [!UICONTROL **Détails**], renseignez les champs suivants :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom**] | Nom du flux de données. Les noms doivent être uniques dans la vue de données sélectionnée et peuvent contenir jusqu’à 255 caractères. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Balises**] | Appliquez des balises au flux de données pour faciliter la catégorisation. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Description**] | Spécifiez une description pour le flux de données. La description que vous ajoutez est visible lors de la modification du flux de données. |
   | [!UICONTROL **Vue de données**] | Sélectionnez la vue de données contenant les données à exporter. |

1. Dans la section [!UICONTROL **Structure de données**], assurez-vous que la vue de données appropriée est sélectionnée dans le champ **[!UICONTROL Vue de données]**. <p>Tenez compte des points suivants lors de la sélection d’une vue de données :</p> <ul><li>Si plusieurs flux de données sont créés pour la même vue de données, chaque flux de données doit avoir des définitions de colonne différentes.</li><li>La liste des colonnes disponibles dépend de la société de connexion à laquelle appartient la vue de données sélectionnée. Si vous modifiez la vue de données, la liste des colonnes disponibles peut changer. </li></ul>

1. Ajoutez des colonnes à la configuration des flux de données. Dans la section du rail des composants à gauche, localisez les colonnes à inclure, puis faites-les glisser vers la zone de travail pour créer votre structure de données. Vous pouvez sélectionner plusieurs colonnes en maintenant la touche **[!UICONTROL Maj]** enfoncée ou en maintenant la touche **[!UICONTROL Commande]** (sous macOS) ou **[!UICONTROL Ctrl]** (sous Windows) enfoncée.

   Utilisez les informations suivantes pour comprendre les dimensions qui sont toujours incluses, les dimensions qui ne peuvent pas être incluses et les mesures qui doivent être remplacées :

   +++ Dimensions toujours incluses dans les flux de données

   Les dimensions suivantes sont incluses par défaut dans chaque flux de données et ne peuvent pas être supprimées :

   | Nom de la dimension | Notes | Flux de données | Autres rapports |
   |---|---|---|---|
   | Date et heure | Date et heure de la période de l’événement. Granularité microseconde. Représenté en UTC. | Obligatoire | Non disponible |
   | ID de ligne | Identifiant de ligne unique | Obligatoire | Non disponible |
   | Identifiant de session | Identifiant unique de chaque session | Obligatoire | Non disponible |
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
   | Profondeur de l’événement | Valeur numérique séquentielle (1, 2, 3, etc.) affecté à chaque interaction d’événement dans une session | Non disponible |
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


1. Dans la section [!UICONTROL **Diffusion**], indiquez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Type de flux**] | Sélectionnez le type de flux que vous souhaitez créer :<ul><li>[!UICONTROL **Flux en direct**] : exporte les données actuelles et futures.</li><li>[!UICONTROL **Flux de renvoi**] : exporte les données historiques comprises entre deux dates antérieures.</li></ul> |
   | [!UICONTROL **Date de début**] | Indiquez la date à laquelle vous souhaitez que le flux de données commence. Pour commencer immédiatement à traiter les flux de données pour les données historiques, assurez-vous que [!UICONTROL **Flux de renvoi**] est sélectionné, puis définissez cette date sur n’importe quelle date dans le passé lorsque des données sont collectées. La date de début est basée sur le fuseau horaire de la vue de données. |
   | [!UICONTROL **Date de fin**] | Indiquez la date à laquelle vous souhaitez que le flux de données se termine. La date de fin est basée sur le fuseau horaire de la vue de données. |
   | [!UICONTROL **Fréquence**] | Sélectionnez la fréquence d’envoi du flux de données. Les événements dont la date et l’heure se trouvent dans la fenêtre de fréquence sont inclus dans la diffusion du flux de données. Les champs [!UICONTROL **Période de recherche en amont**] et [!UICONTROL **Délai de traitement**] peuvent également affecter les événements inclus dans les données pour la fréquence de diffusion que vous choisissez.<p>Pour les flux en direct, sélectionnez cette option pour inclure l’équivalent d’une heure de données ou d’une journée de données. Les flux de renvoi doivent être quotidiens.</p><ul><li>**Quotidien** : les flux contiennent l’équivalent d’une journée complète de données, de minuit à minuit dans le fuseau horaire de la vue de données. Utilisez cette option pour les flux de renvoi ou pour les flux dynamiques.</li><li>**Par heure** : les flux contiennent l’équivalent d’une heure de données. Utilisez cette option pour les flux en direct.</li></ul> |
   | [!UICONTROL **Période de recherche en amont**] | Contrôle le retour en arrière de Customer Journey Analytics lors du traitement de la diffusion du flux de données. <p>Ce paramètre ne modifie pas la fenêtre de fréquence (heure ou jour), qui définit la période des événements à inclure dans la sortie du flux de données. Toutefois, la période de recherche en amont peut influencer les données diffusées, comme suit : </p><ul><li>**Qualification du segment** : lorsqu’un segment est appliqué à votre définition de flux de données, tout événement situé dans la période de recherche en amont détermine si une personne est admissible. Le paramètre de conteneur du segment détermine la portée. (Les conteneurs possibles sont : Personne, Session ou Événement. Le B2B comporte les conteneurs supplémentaires suivants : compte global, compte, opportunité, groupe d’achat.)  <p>Par exemple, si un conteneur Personne est utilisé et que la personne est qualifiée pendant la période de recherche arrière, tous les événements de cette personne pendant la fenêtre de fréquence sont également qualifiés.</p></li><li>**Calcul de session** : les limites de session sont calculées à l’aide de données comprises dans la période de recherche en amont.</li><li>**Transformations de champ dérivé** : toutes les fonctions de champ dérivé qui font référence à des conteneurs utilisent la période de recherche en amont dans les exportations de flux de données.</li><li>**Persistance Dimension** : si vous choisissez de définir la persistance sur une dimension individuelle, vous choisissez également une expiration pour déterminer la durée pendant laquelle un élément de dimension persiste au-delà de l’événement sur lequel il est défini. <p>La période de recherche en amont affecte la persistance des dimensions lorsque l’expiration est définie sur l’une des options suivantes dans la vue de données :</p><ul><li>Pour chaque dimension de la définition de flux de données qui utilise [!UICONTROL **Période de création de rapports**] comme expiration, la période de recherche en amont devient la nouvelle période de création de rapports.</li><li>Pour chaque dimension de la définition du flux de données qui utilise [!UICONTROL **Heure personnalisée**] comme expiration et si l’heure personnalisée sélectionnée s’étend au-delà de la période de recherche en amont, l’heure personnalisée est ignorée et la période de recherche en amont est utilisée pour l’expiration de la dimension.<p>Pour plus d’informations sur la définition de la persistance sur les dimensions dans la vue de données, voir [Paramètres des composants de persistance](/help/data-views/component-settings/persistence.md).</p></li></ul> |
   | [!UICONTROL **Délai de traitement**] | Sélectionnez la durée d’attente avant de traiter un fichier de flux de données. Tous les accès tardifs qui arrivent pendant le délai de traitement sont inclus dans le flux de données. <p>Il peut être utile de mettre en place un délai pour donner aux appareils hors ligne la possibilité de se connecter et d’envoyer leurs données dans le cadre d’implémentations mobiles. Il est également possible d’utiliser un délai pour adapter les processus côté serveur de votre entreprise en ce qui concerne la gestion des fichiers traités précédemment. </p><p>Vous pouvez retarder un flux de 2, 3, 4 ou 8 heures.<p>Pour être incluses, les sessions doivent commencer après la coupure du délai de traitement ; les sessions qui commencent avant la coupure et se terminent dans le délai de traitement ne sont pas incluses.</p> |

1. Dans la section [!UICONTROL **Destination**], configurez la destination vers laquelle vous souhaitez que les données soient envoyées.

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
   | [!UICONTROL **Compte**] | Effectuez l’une des opérations suivantes :<ul><li>**Utiliser un compte existant :** sélectionnez le menu déroulant en regard du champ **[!UICONTROL Compte]**. Vous pouvez également commencer à saisir le nom du compte, puis le sélectionner dans le menu déroulant. <p>Vous ne pouvez accéder aux comptes que si vous les avez configurés ou s’ils sont partagés avec une organisation dont vous faites partie.</p></li><li>**Créer un compte :** sélectionnez **[!UICONTROL Ajouter]** sous le champ **[!UICONTROL Compte]**. Pour plus d’informations sur la configuration du compte, voir [Configuration des comptes d’exportation dans le cloud](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Emplacement**] | Effectuez l’une des opérations suivantes :<ul><li>**Utiliser un emplacement existant :** sélectionnez le menu déroulant en regard du champ **[!UICONTROL Emplacement]**. Vous pouvez également commencer à saisir le nom de l’emplacement, puis le sélectionner dans le menu déroulant.</li><li>**Créer un emplacement :** sélectionnez **[!UICONTROL Ajouter]** sous le champ **[!UICONTROL Emplacement]**. Pour plus d’informations sur la configuration de l’emplacement, voir [Configuration des emplacements d’exportation dans le cloud](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Avertir lorsque l’opération est terminée**] | Indiquez une ou plusieurs adresses e-mail auxquelles une notification doit être envoyée une fois le flux de données envoyé avec succès ou en cas d’échec. Plusieurs adresses e-mail doivent être séparées par une virgule. |
   | [!UICONTROL **Activer le manifeste**] | Choisissez d’inclure un fichier manifeste avec chaque diffusion de flux de données. Le fichier manifeste contient des informations pour chaque fichier inclus dans le flux de données. |

1. Sélectionnez **[!UICONTROL Enregistrer]**.




<!-- why would you want to do this? -->


<!--
I don't think we need anything after this, but saving here just in case:

1. In the [!UICONTROL **Feed Information**] section, complete the following fields:
   
   | Field | Function |
   |---------|----------|
   | [!UICONTROL **Name**] | The name of the data feed. Must be unique within the selected report suite, and can be up to 255 characters in length. [Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique) |
   | [!UICONTROL **Report suite**] | The report suite that the data feed is based on. If multiple data feeds are created for the same report suite, they must have different column definitions. Only source report suites support data feeds; virtual report suites are not supported. |
   | [!UICONTROL **Email when complete**] | The email address to be notified when a feed finishes processing. The email address must be properly formatted. |
   | [!UICONTROL **Feed interval**] | Select **Daily** for backfill or historical data. Daily feeds contain a full day's worth of data, from midnight to midnight in the report suite's time zone. Select **Hourly** for continuing data (Daily is also available for continuing feeds if you prefer). Hourly feeds contain a single hour's worth of data. |
   | [!UICONTROL **Delay processing**] | Wait a given amount of time before processing a data feed file. A delay can be useful to give mobile implementations an opportunity for offline devices to come online and send data. It can also be used to accommodate your organization's server-side processes in managing previously processed files. In most cases, no delay is needed. A feed can be delayed by up to 120 minutes. |
   | [!UICONTROL **Start & end dates**] | The start date indicates the date when you want the data feed to begin. To immediately begin processing data feeds for historical data, set this date to any date in the past when data is being collected. The start and end dates are based on the report suite's time zone. |
   | [!UICONTROL **Continuous feed**] | This checkbox removes the end date, allowing a feed to run indefinitely. When a feed finishes processing historical data, a feed waits for data to finish collecting for a given hour or day. Once the current hour or day concludes, processing begins after the specified delay. |
   
1. In the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select the destination where you want the data to be sent. 

   >[!NOTE]
   >
   >Consider the following when configuring a report destination:
   >
   >* We recommend using a cloud account for your report destination. [Legacy FTP and SFTP accounts](#legacy-destinations) are available, but are not recommended.
   >* Any cloud accounts that you previously configured are available to use for Data Feeds. You can configure cloud accounts in any of the following ways:
   >
   >   * When configuring cloud accounts for [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) 
   >   
   >   * When [importing Adobe Analytics classification data](/help/components/locations/locations-manager.md) (Any locations that are configured for importing classification data cannot be used.)
   >   
   >   * From the Locations manager, in [Components > Locations](/help/components/locations/configure-import-accounts.md) 
   >
   >* Cloud accounts are associated with your Adobe Analytics user account. Other users cannot use or view cloud accounts that you configure.
   >
   >* You can edit any locations that you create from the Locations manager in [Components > Locations](/help/components/locations/configure-import-accounts.md)

   ![Data feed destination drop-down menu](assets/datafeed-destinations-dropdown.png)

   Use any of the following destination types when creating a data feed. For configuration instructions, expand the destination type. (Additional [legacy destinations](#legacy-destinations) are also available, but are not recommended.)

   +++Amazon S3

   You can send feeds directly to Amazon S3 buckets. This destination type requires only your Amazon S3 account and the location (bucket). 

   Adobe Analytics uses cross-account authentication to upload files from Adobe Analytics to the specified location in your Amazon S3 instance.

   When using Amazon S3 with Data Feeds, only SSE-S3 encryption is supported.

   To configure an Amazon S3 bucket as the destination for a data feed:

   1. Begin creating a data feed as described in [Create and configure a data feed](#create-and-configure-a-data-feed).
   
   1. In the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select [!UICONTROL **Amazon S3**].

      ![Amazon S3 destination](assets/datafeed-destination-amazons3.png)

   1. Select [!UICONTROL **Select location**].

      The Amazon S3 Export Locations page is displayed.

   1. (Conditional) If an Amazon S3 account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that were configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).
   
      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

      The destination is now configured to send data to the Amazon S3 location that you specified.
   
   1. (Conditional) If you have not previously added an Amazon S3 account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the account. This can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the account. |
         | [!UICONTROL **Role ARN**] | You must provide a Role ARN (Amazon Resource Name) that Adobe can use to gain access to the Amazon S3 account. To do this, you create an IAM permission policy for the source account, attach the policy to a user, and then create a role for the destination account. For specific information, see [this AWS documentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **User ARN**] | The User ARN (Amazon Resource Name) is provided by Adobe. You must attach this user to the policy you created. |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the account.  |
         | [!UICONTROL **Description**] | A description for the account. |
         | [!UICONTROL **Bucket**] | The bucket within your Amazon S3 account where you want Adobe Analytics data to be sent. <p>Ensure that the User ARN that was provided by Adobe has the `S3:PutObject` permission in order to upload files to this bucket. This permission allows the User ARN to upload initial files and overwrite files for subsequent uploads.</p><p>Bucket names must meet specific naming rules. For example, they must be between 3 to 63 characters long, can consist only of lowercase letters, numbers, dots (.), and hyphens (-), and must begin and end with a letter or number. [A complete list of naming rules are available in the AWS documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
         | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Amazon S3 location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Azure RBAC

   You can send feeds directly to an Azure container by using RBAC authentication. This destination type requires an Application ID, Tenant ID, and Secret. 

   To configure an Azure RBAC account as the destination for a data feed:

   1. If you haven't already, create an Azure application that Adobe Analytics can use for authentication, then grant access permissions in access control (IAM). 
   
      For information, refer to the [Microsoft Azure documentation about how to create an Azure Active Directory application](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal). 
   
   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select [!UICONTROL **Azure RBAC**].

      ![Azure RBAC destination](assets/datafeed-destination-azurerbac.png)

   1. Select [!UICONTROL **Select location**].

      The Azure RBAC Export Locations page is displayed.

   1. (Conditional) If an Azure RBAC account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

      Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure RBAC location that you specified.

   1. (Conditional) If you have not previously added an Azure RBAC account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the Azure RBAC account. This name displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the Azure RBAC account. This description displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose.  |
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information: 
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the location. This name displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Description**] | A description for the location. This description displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account**] | The Azure storage account. |
         | [!UICONTROL **Container**] | The container within the account you specified where you want Adobe Analytics data to be sent. Ensure that you grant permissions to upload files to the Azure application that you created earlier. |
         | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/`<p>Make sure the Application ID that you specified when configuring the Azure RBAC account has been granted the `Storage Blob Data Contributor` role in order to access the container (folder).</p> <p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure RBAC location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Azure SAS

   You can send feeds directly to an Azure container by using SAS authentication. This destination type requires an Application ID, Tenant ID, Key vault URI, Key vault secret name, and secret. 

   To configure Azure SAS as the destination for a data feed:

   1. If you haven't already, create an Azure application that Adobe Analytics can use for authentication. 
   
      For information, refer to the [Microsoft Azure documentation about how to create an Azure Active Directory application](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal). 
   
   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, select [!UICONTROL **Azure SAS**].

      ![Azure SAS destination](assets/datafeed-destination-azuresas.png)

   1. Select [!UICONTROL **Select location**].

      The Azure SAS Export Locations page is displayed.

   1. (Conditional) If an Azure SAS account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure SAS location that you specified.
   
   1. (Conditional) If you have not previously added an Azure SAS account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the Azure SAS account. This name displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the Azure SAS account. This description displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Key vault URI**] | <p>The path to the SAS URI in Azure Key Vault. To configure Azure SAS, you need to store an SAS URI as a secret using Azure Key Vault. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>After the key vault URI is created:<ul><li>Add an access policy on the Key Vault in order to grant permission to the Azure application that you created.<p>For information, see the [Microsoft Azure documentation about how to assign a Key Vault access policy](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>Or</p><p>If you want to grant an access role directly without creating an access policy, see the [Microsoft Azure documentation about how to assign Azure roles using Azure portal](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). This adds the role assignment for the application ID to access the key vault URI. </p></li><li>Make sure the Application ID has been granted the `Key Vault Certificate User` built-in role in order to access the key vault URI.</br><p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul> |
         | [!UICONTROL **Key vault secret name**] | The secret name you created when adding the secret to Azure Key Vault. In Microsoft Azure, this information is located in the Key Vault you created, on the **Key Vault** settings pages. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information: 
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the location. This name displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Description**] | A description for the location. This description displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Container**] | The container within the account you specified where you want Adobe Analytics data to be sent. |
         | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/`<p>Make sure that the SAS URI store that you specified in the Key Vault secret name field when configuring the Azure SAS account has the `Write` permission. This allows the SAS URI to create files in your Azure container. <p>If you want the SAS URI to also overwrite files, make sure that the SAS URI store has the `Delete` permission.</p><p>For more information, see [Blob storage resources](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) in the Azure Blob Storage documentation.</p> |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure SAS location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Google Cloud Platform

   You can send feeds directly to Google Cloud Platform (GCP) buckets. This destination type requires only your GCP account name and the location (bucket) name. 
   
   Adobe Analytics uses cross-account authentication to upload files from Adobe Analytics to the specified location in your GCP instance.

   To configure a GCP bucket as the destination for a data feed:

   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, select [!UICONTROL **Google Cloud Platform**].

      ![Google Cloud Platform destination](assets/datafeed-destination-gcp.png)

   1. Select [!UICONTROL **Select location**].

      The GCP Export Locations page is displayed.

   1. (Conditional) If a Google Cloud Platform account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Google Cloud Platform location that you specified.
   
   1. (Conditional) If you have not previously added a GCP account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the account. This can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the account. |
         | [!UICONTROL **Project ID**] | Your Google Cloud project ID. See the [Google Cloud documentation about getting a project ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Principal**] | The Principal is provided by Adobe. You must grant permission to receive feeds to this principal. |
         | [!UICONTROL **Name**] | A name for the account.  |
         | [!UICONTROL **Description**] | A description for the account. |
         | [!UICONTROL **Bucket**] | The bucket within your GCP account where you want Adobe Analytics data to be sent. <p>Ensure that you have granted either of the following permissions to the Principal provided by Adobe: (For information about granting permissions, see [Add a principal to a bucket-level policy](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) in the Google Cloud documentation.)<ul><li>`roles/storage.objectCreator`: Use this permission if you  want to limit the Principal to only create files in your GCP account. </br>**Important:** If you use this permission with scheduled reporting, you must use a unique file name for each new scheduled export. Otherwise, the report generation will fail because the Principal does not have access to overwrite existing files.</li><li>(Recommended) `roles/storage.objectUser`: Use this permission if you want the Principal to have access to view, list, update, and delete files in your GCP account.</br>This permission allows the Principal to overwrite existing files for subsequent uploads, without the need to auto-generate unique file names for each new scheduled export.</li></ul><p>If your organization is using [Organization policy constraints](https://cloud.google.com/storage/docs/org-policy-constraints) to allow only the Google Cloud Platform account in your allow list, you need the following Adobe-owned Google Cloud Platform organization ID: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
         | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the GCP location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

1. In the  [!UICONTROL **Data Column Definitions**] section, select the latest [!UICONTROL **All Adobe Columns**] template in the drop-down menu, then complete the following fields:
   
   |Field | Function |
   |---------|----------|
   | [!UICONTROL **Remove escaped characters**] | When collecting data, some characters (such as newlines) can cause issues. Check this box if you would like these characters removed from feed files. |
   | [!UICONTROL **Compression format**] | The type of compression used. **Gzip** outputs files in `.tar.gz` format. **Zip** outputs files in `.zip` format. |
   | [!UICONTROL **Packaging type**] | Select [!UICONTROL **Multiple files**] for most data feeds. This option paginates your data into uncompressed 2GB chunks. (If the [!UICONTROL **Multiple files**] option is selected and uncompressed data for the reporting window is less than 2GB, one file is sent.) Selecting **Single file** outputs the `hit_data.tsv` file in a single, potentially massive file. |
   | [!UICONTROL **Manifest**] | Determines whether Adobe should deliver a [manifest file](c-df-contents/datafeeds-contents.md#feed-manifest) to the destination when no data is collected for a feed interval. If you select **Manifest File**, you receive a manifest file similar to the following when no data is collected:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Column templates**] | When creating many data feeds, Adobe recommends creating a column template. Selecting a column template automatically includes the specified columns in the template. Adobe also provides several templates by default. |
   | [!UICONTROL **Available columns**] | All available data columns in Adobe Analytics. Click [!UICONTROL Add all] to include all columns in a data feed. |
   | [!UICONTROL **Included columns**] | The columns to include in a data feed. Click [!UICONTROL Remove all] to remove all columns from a data feed. |
   | [!UICONTROL **Download CSV**] | Downloads a CSV file containing all included columns. |

1. Select [!UICONTROL **Save**] in the top-right.

    Historical data processing begins immediately. When data finishes processing for a day, the file is sent to the destination that you configured.

    For information about how to access the data feed and to get a better understanding of its contents, see [Data feed contents - overview](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Legacy destinations

>[!IMPORTANT]
>
>The destinations described in this section are legacy, and are not recommended. Instead, use one of the following destinations when creating a data feed: Amazon S3, Google Cloud Platform, Azure RBAC, or Azure SAS. See [Create and configure a data feed](#create-and-configure-a-data-feed) for detailed information about each of these recommended destinations. 


The following information provides configuration information for each of the legacy destinations:

### FTP

Data feed data can be delivered to an Adobe or customer-hosted FTP location. Requires an FTP host, username, and password. Use the path field to place feed files in a folder. Folders must already exist; feeds throw an error if the specified path does not exist.

Use the following information when completing the available fields:

* [!UICONTROL **Host**]: Enter the desired FTP destination URL. For example, `ftp://ftp.omniture.com`.
* [!UICONTROL **Path**]: Can be left blank
* [!UICONTROL **Username**]: Enter the username to log in to the FTP site.
* [!UICONTROL **Password and confirm password**]: Enter the password to log in to the FTP site.

### SFTP

SFTP support for data feeds is available. Requires an SFTP host, username, and the destination site to contain a valid RSA or DSA public key. You can download the appropriate public key when creating the feed.

### S3

You can send feeds directly to Amazon S3 buckets. This destination type requires a Bucket name, an Access Key ID, and a Secret Key. See [Amazon S3 bucket naming requirements](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) within the Amazon S3 docs for more information.

The user you provide for uploading data feeds must have the following [permissions](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >For each upload to an Amazon S3 bucket, [!DNL Analytics] adds the bucket owner to the BucketOwnerFullControl ACL, regardless of whether the bucket has a policy that requires it. For more information, see "[What is the BucketOwnerFullControl setting for Amazon S3 data feeds?](df-faq.md#BucketOwnerFullControl)"

The following 16 standard AWS regions are supported (using the appropriate signature algorithm where necessary):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>The cn-north-1 region is not supported.

### Azure Blob

Data feeds support Azure Blob destinations. Requires a container, account, and a key. Amazon automatically encrypts the data at rest. When you download the data, it gets decrypted automatically. See [Create a storage account](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) within the Microsoft Azure docs for more information.

>[!NOTE]
>
>You must implement your own process to manage disk space on the feed destination. Adobe does not delete any data from the server.

-->
