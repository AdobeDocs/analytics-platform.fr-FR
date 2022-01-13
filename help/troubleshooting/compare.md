---
title: Comparer vos données AA aux données CJA
description: Découvrez comment comparer vos données Adobe Analytics aux données dans Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: 6f77dd9caef1ac8c838f825a48ace6cf533d28a9
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 5%

---

# Comparer vos données Adobe Analytics aux données CJA

Supposons que vous ayez ingéré des données Adobe Analytics dans AEP via Analytics Source Connector, puis créé une connexion CJA à l’aide de ce jeu de données.

![flux de données](assets/compare.png)

Ensuite, vous avez créé une vue de données et, lors de la création de rapports ultérieure sur ces données sur CJA, vous avez remarqué des incohérences avec les résultats de la création de rapports dans Adobe Analytics.

Voici quelques étapes à suivre pour comparer vos données Adobe Analytics d’origine aux données Adobe Analytics qui sont désormais en Customer Journey Analytics.

## Conditions préalables

* Assurez-vous que le jeu de données Analytics dans AEP contient des données pour la période sur laquelle vous enquêtez.

* Assurez-vous que la suite de rapports sélectionnée dans Analytics correspond à la suite de rapports ingérée dans Adobe Experience Platform.

## Étape 1 : Exécution de la mesure Occurrences dans Adobe Analytics

Le [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr) indique le nombre d’accès pour lesquels une dimension donnée a été définie ou conservée.

1. Dans Analytics > [!UICONTROL Workspace], faites glisser la période sur laquelle vous souhaitez créer un rapport en tant que dimension dans un [!UICONTROL Structure libre] table.

1. Le [!UICONTROL Occurrences] est automatiquement appliquée à cette période.

1. Enregistrez ce projet afin que vous puissiez l’utiliser dans la comparaison.

## Étape 2 : Comparer les résultats à [!UICONTROL Total des enregistrements par horodatage] dans CJA

Comparez maintenant la variable [!UICONTROL Occurrences] dans Analytics au total des enregistrements par horodatages dans Customer Journey Analytics.

Le nombre total d’enregistrements par horodatage doit correspondre au nombre d’occurrences, à condition qu’aucun enregistrement n’ait été déposé par le connecteur source Analytics - voir la section ci-dessous.

>[!NOTE]
>
>Cela fonctionne uniquement pour les jeux de données de valeurs moyennes standard, et non pour les jeux de données assemblés (via [Analyse cross-canal](/help/connections/cca/overview.md)). Veuillez noter que la prise en compte de l’ID de personne utilisé dans CJA est essentielle pour faire fonctionner la comparaison. Cela peut ne pas être toujours facile à répliquer dans AA, en particulier si l’analyse cross-canal a été activée.

1. Dans Adobe Experience Platform [Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html), exécutez les opérations suivantes [!UICONTROL Nombre total d’enregistrements par horodatage] query :

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

1. Dans [Flux de données Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr), déterminez dans les données brutes si certaines lignes ont pu être perdues par le connecteur source Analytics.

   Le [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) peut déposer des lignes pendant la transformation vers le schéma XDM. Il peut y avoir de multiples raisons pour que toute la rangée soit inadaptée à la transformation. Si l’un des champs Analytics suivants possède ces valeurs, la ligne entière sera supprimée.

   | Champ Analytics | Valeurs qui le font disparaître |
   | --- | --- |
   | Opt_out | `y, Y` |
   | In_data_only | Pas 0 |
   | Exclure_hit | Pas 0 |
   | Bot_id | Pas 0 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 53 63 |

1. Si le connecteur fait glisser des lignes, soustrayez ces lignes de la [!UICONTROL Occurrences] mesure. Le nombre obtenu doit correspondre au nombre d’événements dans les jeux de données Adobe Experience Platform.

## Raisons pour lesquelles des enregistrements peuvent être ignorés ou ignorés lors de l’ingestion à partir d’AEP

CJA [Connexions](/help/connections/create-connection.md) vous permettent de rassembler et de joindre plusieurs jeux de données en fonction d’un ID de personne commun dans les jeux de données. Sur le serveur principal, nous appliquons la déduplication : jointure externe ou union complète sur des jeux de données d’événement en fonction des horodatages, puis jointure interne sur le jeu de données de profil et de recherche, en fonction de l’ID de personne.

Voici quelques-unes des raisons pour lesquelles les enregistrements peuvent être ignorés lors de l’ingestion de données à partir d’AEP.

* **Horodatages manquants** - Si les jeux de données d’événement ne contiennent pas d’horodatages, ces enregistrements seront totalement ignorés ou ignorés lors de l’ingestion.

* **ID de personne manquants** - Les identifiants de personne manquants (du jeu de données d’événements et/ou du jeu de données de profil/recherche) font que ces enregistrements sont ignorés ou ignorés. La raison en est qu’il n’existe pas d’ID communs ou de clés correspondantes pour rejoindre les enregistrements.

* **ID de personne non valide ou volumineuse** - Avec les identifiants non valides, le système ne trouve pas d’identifiant commun valide parmi les jeux de données à joindre. Dans certains cas, la colonne ID de personne comporte des ID de personne non valides tels que &quot;non défini&quot; ou &quot;00000000&quot;. Un ID de personne (avec toute combinaison de nombres et de lettres) qui apparaît dans un événement plus de 1 million de fois par mois ne peut être attribué à aucun utilisateur ou personne spécifique. Il sera classé comme non valide. Ces enregistrements ne peuvent pas être ingérés dans le système, ce qui entraîne l’ingestion et la création de rapports sujets aux erreurs.
