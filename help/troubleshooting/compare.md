---
title: Comparer vos données AA aux données CJA
description: Découvrez comment comparer vos données Adobe Analytics aux données dans Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: 718dc00b13ec0a79e122b4a2ca48f4de7643bacb
workflow-type: ht
source-wordcount: '825'
ht-degree: 100%

---

# Comparaison de vos données Adobe Analytics aux données CJA

Suite à lʼadoption de CJA par votre organisation, vous pouvez constater certaines différences entre les données Adobe Analytics et CJA. Cette situation est normale et peut se produire pour plusieurs raisons. CJA est conçu pour vous permettre de remédier à certaines des limites imposées à vos données dans AA. Cependant, des incohérences inattendues peuvent se produire. Cet article est conçu pour vous aider à diagnostiquer et à résoudre ces différences, afin que vous et votre équipe puissiez utiliser CJA sans vous soucier de lʼintégrité des données.

Prenons le scénario suivant : vous avez ingéré des données Adobe Analytics dans AEP, via le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr), puis créé une connexion CJA à l’aide de ce jeu de données.

![flux de données](assets/compare.png)

Ensuite, vous avez créé une vue de données, puis établi des rapports sur ces données dans CJA. Vous avez alors constaté des incohérences par rapport aux résultats des rapports dans Adobe Analytics.

Effectuez la procédure suivante pour comparer vos données Adobe Analytics d’origine avec les données Adobe Analytics qui se trouvent maintenant dans Customer Journey Analytics.

## Conditions préalables

* Assurez-vous que le jeu de données Analytics dans AEP contient des données pour la période recherchée.

* Veillez également à ce que la suite de rapports sélectionnée dans Analytics corresponde à la suite de rapports ingérée dans Adobe Experience Platform.

## Étape 1 : exécution de la mesure Occurrences dans Adobe Analytics

La mesure [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr) indique le nombre d’accès pour lesquels une dimension donnée a été définie ou conservée.

1. Dans Analytics > [!UICONTROL Espace de travail], faites glisser la période pour laquelle vous souhaitez créer un rapport en tant que dimension dans un tableau à [!UICONTROL Structure libre].

1. La mesure [!UICONTROL Occurrences] est automatiquement appliquée à cette période.

1. Enregistrez ce projet afin de l’utiliser dans la comparaison.

## Étape 2 : comparaison des résultats au [!UICONTROL Nombre total des enregistrements par horodatage] dans CJA

Comparez maintenant les [!UICONTROL Occurrences] dans Analytics au nombre total des enregistrements par horodatage dans Customer Journey Analytics.

Le nombre total d’enregistrements par horodatage doit correspondre aux Occurrences, à condition qu’aucun enregistrement n’ait été ignoré par le connecteur source Analytics (voir la section ci-dessous).

>[!NOTE]
>
>Cela fonctionne uniquement pour les jeux de données de valeurs moyennes standard, et non pour les jeux de données assemblés (via lʼ[Cross-Channel Analytics](/help/connections/cca/overview.md)). Notez que la prise en compte de l’ID de personne utilisé dans CJA est essentielle pour que la comparaison fonctionne. Cette procédure nʼest pas toujours facile à répliquer dans AA, en particulier si l’Cross-Channel Analytics a été activée.

1. Dans les [services de requête](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=fr) dʼAdobe Experience Platform, exécutez la requête suivante [!UICONTROL Nombre total d’enregistrements par horodatage] :

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. Dans les [Flux de données Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr), identifiez parmi les données brutes si certaines lignes ont pu être ignorées par le connecteur source Analytics.

   Le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) peut ignorer des lignes pendant la transformation en schéma XDM. Plusieurs raisons peuvent expliquer pourquoi la ligne entière ne satisfait pas aux conditions de transformation. Si l’un des champs Analytics suivants possède ces valeurs, la ligne entière sera abandonnée.

   | Champ Analytics | Valeurs qui entraînent la suppression d’une ligne |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | Pas 0 |
   | Exclude_hit | Pas 0 |
   | Bot_id | Pas 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   Pour plus d’informations sur hit\_source, voir : [Référence des colonnes de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr). Pour plus d’informations sur page\_event, voir : [Recherche d’événement de page](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=fr).

1. Si le connecteur a ignoré des lignes, soustrayez ces lignes de la mesure [!UICONTROL Occurrences]. Le nombre obtenu doit correspondre au nombre d’événements dans les jeux de données Adobe Experience Platform.

## Raisons pour lesquelles des enregistrements peuvent être abandonnés ou ignorés lors de l’ingestion à partir d’AEP

Les [Connexions](/help/connections/create-connection.md) CJA vous permettent de rassembler et de joindre plusieurs jeux de données en fonction d’un ID de personne commun à tous les jeux de données. Sur le serveur principal, nous appliquons la déduplication : jointure externe complète ou union sur les jeux de données d’événement basés sur les horodatages, puis jointure interne sur les jeux de données de profil et de recherche, basés sur l’ID de personne.

Voici quelques-unes des raisons pour lesquelles des enregistrements peuvent être ignorés lors de l’ingestion de données à partir d’AEP.

* **Horodatages manquants** : si les jeux de données d’événement ne contiennent pas d’horodatage, ces enregistrements seront abandonnés ou ignorés lors de l’ingestion.

* **ID de personne manquants** : si les ID de personne sont manquants (du jeu de données d’événements et/ou du jeu de données de profil/recherche), les enregistrements sont abandonnés ou ignorés. Cela est dû au fait qu’aucun identifiant commun ni de clé correspondante nʼexiste pour joindre les enregistrements.

* **ID de personne non valide ou de grande taille** : en cas dʼID non valides, le système ne peut pas trouver un identifiant commun valide parmi les jeux de données à joindre. Dans certains cas, la colonne ID de personne comporte des ID de personne non valides tels que « undefined » ou « 00000000 ». Un ID de personne (avec nʼimporte quelle combinaison de chiffres et de lettres) qui apparaît dans un événement plus dʼun million de fois par mois ne peut être attribué à un utilisateur ou une personne spécifique. Il sera classé comme non valide. Ces enregistrements ne peuvent pas être ingérés dans le système et entraînent une ingestion et un compte rendu des performances sujets aux erreurs.
