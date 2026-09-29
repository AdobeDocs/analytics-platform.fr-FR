---
title: Utilisation des résultats mis en cache pour un chargement plus rapide dans Analysis Workspace
description: Activez un paramètre de projet dans Analysis Workspace qui met en cache les résultats de la requête pendant 12 heures afin que les projets se chargent instantanément. Actualisez à tout moment pour afficher les dernières données.
feature: Workspace Basics
hide: true
exl-id: 6d7b9d34-ec7e-45ec-98cc-0fd4cbfd43d3
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 80ce27bcff09a23e38054e05329a2a261c8f6562
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 0%
---

# Utilisation des résultats mis en cache dans les projets Workspace

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Utilisation des résultats mis en cache pour un chargement plus rapide"
>abstract="Lorsqu’ils sont activés, les résultats se chargent instantanément pendant 12 heures après la première ouverture d’un projet par un utilisateur ou une utilisatrice ou leur diffusion selon un planning. Quiconque ouvre le projet pendant cette période voit les mêmes résultats, même si les données continuent de circuler en arrière-plan. Pour charger les derniers résultats, actualisez les panneaux individuels ou l’ensemble du projet."

Vous pouvez configurer des projets Analysis Workspace pour qu’ils affichent les résultats mis en cache pendant 12 heures, ce qui permet aux résultats de se charger instantanément pour toute personne qui ouvre le projet après son chargement initial.

Les projets peuvent être initialement chargés par un utilisateur qui ouvre le projet ou par une diffusion de projet planifiée.

>[!NOTE]
>
>Seuls les résultats de la requête sont mis en cache. Les données d’événement sous-jacentes continuent de circuler dans Customer Journey Analytics comme d’habitude.
>
>Pour afficher les dernières données avant l’expiration des résultats mis en cache, vous pouvez [actualiser manuellement les résultats](#manually-refresh-results-on-cached-projects).

## Présentation des résultats mis en cache dans un projet

### Lorsque les résultats sont mis en cache

Lors de la première exécution du projet, Analysis Workspace exécute la requête comme d’habitude et met en cache les résultats pendant 12 heures. Cela se produit lorsque quelqu’un ouvre le projet ou lorsque le projet s’exécute pour une diffusion planifiée. Par exemple, si la diffusion d’un projet est planifiée à 6 heures du matin, les résultats sont mis en cache jusqu’à 18 heures. Toute personne ouvrant le projet entre 6 h et 18 h voit les résultats se charger instantanément, y compris la première personne à l’ouvrir.

Au bout de 12 heures, les résultats mis en cache expirent. La requête suivante sur le projet, si un utilisateur l’ouvre ou si une diffusion planifiée s’exécute, se charge à une vitesse normale et démarre une nouvelle fenêtre de 12 heures.

### Quels résultats sont mis en cache

Analysis Workspace met en cache chaque requête qui s’exécute, et non toutes les versions possibles d’un projet.

Lorsqu’une personne modifie la requête dans un projet (en sélectionnant un élément dans un menu déroulant de panneau ou en appliquant un segment, par exemple), Analysis Workspace exécute une nouvelle requête. La nouvelle requête se charge à une vitesse normale la première fois. Ensuite, ses résultats sont également mis en cache, de sorte que les personnes exécutant la même requête voient les résultats instantanément.

La mise en cache d’une nouvelle requête ne remplace ni n’invalide les résultats déjà mis en cache. L’affichage du projet d’origine est mis en cache avec d’autres variations que les personnes ont exécutées.

>[!BEGINSHADEBOX]

**Exemple de scénario**

Supposons qu’un projet Performances de campagne globale comprenne des segments pour différentes régions et qu’il soit programmé pour une diffusion à 6 h 00 :

| Heure | Action | Vitesse de charge |
| --- | --- | --- |
| 6 h 00 | Diffusion planifiée du projet | Normale (les résultats sont mis en cache pour une utilisation ultérieure) |
| 07:06 | L’utilisateur A ouvre le projet | Instantané |
| 07:06 | L’utilisateur A applique le segment Amériques | Normale (les résultats sont mis en cache pour une utilisation ultérieure) |
| 08:01 | L’utilisateur B ouvre le projet | Instantané |
| 08:01 | L’utilisateur B applique le segment Amériques | Instantané |
| 08:01 | L’utilisateur B applique le segment EMEA | Normale (les résultats sont mis en cache pour une utilisation ultérieure) |

>[!ENDSHADEBOX]

### Qui voit les résultats mis en cache

Les résultats mis en cache s’affichent par défaut pour toutes les personnes qui :

* A accès au projet

* A accès aux vues de données utilisées dans le projet

* Utilise les mêmes paramètres de requête dans le projet qui ont été précédemment mis en cache (par exemple, le projet qu’ils visualisent utilise les mêmes segments ou sélections de listes déroulantes de panneau qu’un projet précédemment mis en cache)

Lors de l’affichage des résultats mis en cache, vous pouvez afficher les données les plus récentes en [actualisant manuellement les résultats](#manually-refresh-results-on-cached-projects).

## Activer les résultats mis en cache pour un projet

Toute personne pouvant mettre à jour les paramètres du projet peut activer les résultats mis en cache. Cela inclut le propriétaire du projet et toute personne disposant du rôle **[!UICONTROL Modifier l’original]** pour le projet. Pour plus d’informations sur les rôles de projet, voir [Partager un rôle de projet spécifique](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

Dans le projet Workspace dans lequel vous souhaitez activer les résultats mis en cache pour un chargement quasi instantané :

1. Accédez à **[!UICONTROL Projets]** > **[!UICONTROL Informations et paramètres du projet]**.
1. Sélectionnez **[!UICONTROL Utiliser les résultats mis en cache pour accélérer le chargement]**.
1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Afficher les résultats mis en cache dans un projet

Un horodatage s’affiche en haut du projet lorsque les résultats mis en cache sont affichés. La date et l’heure indiquent si tous les résultats sont mis en cache ou seulement certains d’entre eux :

* **[!UICONTROL Affichage des résultats à partir du] [_date et heure_]**: tous les panneaux du projet affichent les résultats en mémoire cache de la date et de l’heure affichées.
* **[!UICONTROL Affichage de certains résultats à partir de] [_date et heure_]**: certains panneaux affichent les résultats mis en cache à partir de la date et de l’heure affichées, tandis que d’autres ont été actualisés plus récemment.

![Date et heure du projet mis en cache](assets/project-cache-timestamp.png)

Les panneaux affichent également un horodatage indiquant le moment où les résultats ont été mis en cache :

* **[!UICONTROL Affichage des résultats à partir de] [_date et heure_]**: le panneau affiche les résultats mis en cache à partir de la date et de l’heure affichées.

  >[!NOTE]
  >
  >Cette option n’est pas disponible pendant la phase alpha de la version.

## Actualisation manuelle des résultats sur les projets mis en cache

Vous pouvez actualiser manuellement les résultats d’un projet à tout moment pendant la période de 12 heures afin d’afficher les dernières données. Lorsque vous actualisez l’ensemble du projet, une nouvelle fenêtre de 12 heures commence et toutes les personnes qui ouvrent le projet pendant cette fenêtre voient les résultats actualisés.

Dans le projet Workspace dans lequel vous souhaitez afficher les dernières données, vous pouvez actualiser les résultats pour l’ensemble du projet ou pour un seul panneau.

### Actualiser les résultats pour l’ensemble du projet

Pour charger les derniers résultats pour tous les panneaux et démarrer une nouvelle fenêtre de 12 heures :

1. Sélectionnez l’icône **[!UICONTROL Actualiser]** ![Actualiser](/help/assets/icons/Refresh.svg) en haut du projet à côté de la date et de l’heure du projet.

### Actualiser les résultats pour un seul panneau

>[!NOTE]
>
>Cette option n’est pas disponible pendant la phase alpha de la version.

Pour charger les derniers résultats pour un seul panneau uniquement :

1. Sélectionnez l’icône **[!UICONTROL Actualiser]** ![Actualiser](/help/assets/icons/Refresh.svg) en haut du projet à côté de la date et de l’heure d’un panneau.

