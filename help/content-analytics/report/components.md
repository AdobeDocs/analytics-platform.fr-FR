---
title: Composants de Content Analytics
description: Détails sur les composants spécifiques de Content Analytics, tels que les dimensions, les mesures (calculées) et les champs dérivés
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '1390'
ht-degree: 17%

---

# Composants de Content Analytics

>[!WARNING]
>
>Cet article est un avant-projet non officiel d’une version finale à venir et fait partie de la documentation de Content Analytics. Tout le contenu est sujet à modification et aucune obligation légale quelle qu&#39;elle soit ne peut être dérivée de la version actuelle de cet article.
>

{{release-limited-testing}}

Content Analytics ajoute les catégories de composants suivantes (dimensions, mesures (calculées), champs dérivés) aux composants déjà disponibles dans Customer Journey Analytics :

* [Métadonnées d’expérience](#experience-metadata)
* [Attributs de l’expérience](#experience-attributes)
* [Événements d’expérience](#experience-events)
* [Métadonnées de ressource](#asset-metadata)
* [Attributs de la ressource](#asset-attributes)
* [Événements Assets](#asset-events)
* [Mesures calculées](#calculated-metrics)

Dans les tableaux ci-dessous, ![IA générée](/help/assets/icons/AI.svg) indique une valeur générée par IA/ML.

## Métadonnées d’expérience

| Titre | Description | Type | Paramètres |
|---|---|---|---|
| Canal d’expérience | Canal pour l’expérience. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Source de l’expérience | URL Source de l’expérience. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Identifiant d’expérience | ID unique de l’expérience. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Nom de l’expérience | Nom de l’expérience. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Description de l’expérience | Description de l’expérience. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| URL de miniature de l’expérience | URL de la miniature de l’expérience. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Profondeur horizontale de l’expérience en pourcentage | Valeur quantifiable de la profondeur horizontale en pourcentage de l’expérience. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Profondeur verticale de l’expérience en pourcentage | Valeur quantifiable de la profondeur verticale en pourcentage de l’expérience. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Profondeur horizontale de l’expérience en pixels | Valeur quantifiable de la profondeur horizontale en pixels de l’expérience. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Profondeur verticale de l’expérience en pixels | Valeur quantifiable de la profondeur verticale en pixels de l’expérience. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |

{style="table-layout:fixed"}



## Attributs de l’expérience

| Titre | Description | Type | Paramètres |
|---|---|---|---|
| Score de lisibilité de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Score de lisibilité de l’expérience. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Mots-clés de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Mots-clés pour l’expérience. | Champ <br> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Stratégies de persuasion de l’expérience | ![générées par l’IA](/help/assets/icons/AI.svg) Stratégies de persuasion présentes dans l’expérience donnée. Les valeurs possibles sont : l’identité sociale, la preuve sociale, l’autorité, le concret, le pied dans la porte, surmonter la réactance, la réciprocité, l’ancrage et la comparaison, l’impact social, la rareté et l’anthropomorphisme. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Narrations de l’expérience | ![généré par l’IA](/help/assets/icons/AI.svg) Récits que l’expérience crée en fonction de la pertinence du point de vue d’un spécialiste marketing. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Tons de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Tons que l’expérience crée en fonction de la pertinence du point de vue d’un spécialiste marketing | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Émotions marketing de l’expérience | ![L’IA générée](/help/assets/icons/AI.svg) L’émotion invoquée par le lecteur à la lecture du texte utilisé dans le cadre de l’expérience : Urgence, Exclusivité, Encouragement, Défi, Curiosité, Réussite, Confiance, Simplicité et Fascination. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Nombre d’émoticônes de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre d’émoticônes pour l’expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |
| Nombre de hashtags de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de hashtags pour l&#39;expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |
| Nombre de phrases de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de phrases pour l’expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |
| Taux de mots vides de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de mots vides pour l’expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |
| Nombre de citations de texte de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de guillemets pour l’expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |
| Nombre de mots de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de mots pour l’expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |
| Nombre de mots de l’expérience par phrase | ![IA générée](/help/assets/icons/AI.svg) Nombre de mots par phrase pour l’expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |

{style="table-layout:fixed"}


## Événements d’expérience

| Titre | Description | Type | Paramètres |
|---|---|---|---|
| Vues d’expérience | Mesure quantifiable du nombre de vues de l’expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |
| Clics sur l’expérience | Mesure quantifiable du nombre de clics de l’expérience. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |

{style="table-layout:fixed"}


## Métadonnées de ressource

| Titre | Description | Type | Paramètres |
|---|---|---|---|
| Source de la ressource | URL source accessible au public pour la ressource. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| ID de ressource | Identifiant unique de la ressource. Le fichier binaire de la ressource détermine l’unicité. Si le fichier binaire de la ressource change, l’identifiant change. L’ID unique peut être l’URL, mais il peut également s’agir d’un hachage créé. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Nom de la ressource | Nom de la ressource. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Type de ressource | Type de la ressource. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| URL des miniatures de la ressource | URL de la miniature de la ressource. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Chemin HTML de la ressource | Chemin HTML concaténé pour la ressource. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| URL du lien de la ressource | Ancre de page la plus proche pour la ressource. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Largeur d’affichage de la ressource | Largeur d’affichage de la ressource de contenu. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Hauteur d’affichage de la ressource | Hauteur d’affichage de la ressource de contenu. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Gauche absolue de la ressource | Gauche absolue de la ressource de contenu. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Première position absolue de la ressource | Première position absolue de la ressource de contenu. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Ressource créée par | Identifiant pour la création de la ressource. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Date de création de la ressource | Date de création de la ressource. | Dimension | La plus récente \| Session |
| Dernière mise à jour de la ressource par | Identifiant pour la mise à jour de la ressource. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Date de la dernière mise à jour de la ressource | Date de mise à jour de la ressource. | Dimension | La plus récente \| Session |

{style="table-layout:fixed"}


## Attributs de la ressource

| Titre | Description | Type | Paramètres |
|---|---|---|---|
| Orientation de la ressource | ![IA générée](/help/assets/icons/AI.svg) Orientation de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Ton général de la ressource | ![IA générée](/help/assets/icons/AI.svg) Ton global de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Couleurs du premier plan de la ressource | ![IA générée](/help/assets/icons/AI.svg) Couleurs de premier plan de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Couleur d’arrière-plan des ressources | ![IA générée](/help/assets/icons/AI.svg) Couleurs d’arrière-plan de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Balises de la ressource | ![IA générée](/help/assets/icons/AI.svg) Balises de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Scènes de ressource | ![IA générée](/help/assets/icons/AI.svg) Scènes pour la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Objets de la ressource | ![IA générée](/help/assets/icons/AI.svg) Objets de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Styles de photographie de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) Styles de photographie de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Type d’image de la ressource | ![IA générée](/help/assets/icons/AI.svg) Type d’image de la ressource. Les valeurs possibles sont les suivantes : photographie, schéma, peinture, dessin animé numérique, infographie, conception graphique, collage et capture d’écran du logiciel. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Positions des caméras de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) positions de la caméra de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Proximités des caméras de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) Proximité de la caméra de la ressource. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Catégories de personnes de la ressource | ![IA générée](/help/assets/icons/AI.svg) Catégories de personnes pour la ressource. Les valeurs possibles sont les suivantes : personne, homme, femme, groupe social, foule, personnes, garçon, fille et enfant. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Densité du contenu visuel de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) Densité de contenu visuel de la ressource. Les valeurs possibles sont : faible, moyenne ou élevée. Une faible densité de contenu implique une petite quantité d’informations présentes par unité de surface de l’image. | Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Diffusion d’attention visuelle de la ressource | ![IA générée](/help/assets/icons/AI.svg) Répartition de l’attention visuelle de la ressource. Les valeurs possibles sont : faible, moyenne ou élevée. La dispersion de l&#39;attention fait référence à la mesure dans laquelle l&#39;attention d&#39;un spectateur est divisée entre différentes parties d&#39;une image. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Condition d’éclairage de la ressource | ![IA générée](/help/assets/icons/AI.svg) Condition d’éclairage de la ressource. Les valeurs possibles sont les suivantes : heure d’or, heure bleue, midi, ciel couvert, nuit, haute résolution, basse résolution, éclairage naturel, incandescent, fluorescent, coloré et studio. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |
| Paramètres de la caméra de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) Paramètre de caméra de la ressource. Les valeurs possibles sont : vitesse d&#39;obturation rapide, exposition longue. flou boréal, flou animé, flou avec décalage d&#39;inclinaison, flash, grand angle, noir et blanc, surréaliste, double exposition, macro et mode normal. | Champ <br/> Dimension | Afficher \| Aucune valeur<br/>La plus récente \| Session |

{style="table-layout:fixed"}


## Événements de ressource

| Titre | Description | Type | Paramètres |
|---|---|---|---|
| Vues des ressources | Mesure quantifiable du nombre de vues de la ressource. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |
| Clics sur les ressources | Mesure quantifiable du nombre de clics sur la ressource. | Mesure | Compter les valeurs<br/>Décimal \| Nombre de décimales : 0 |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## Mesures calculées

| Titre | Description | Type | Paramètres |
|---|---|---|---|
| Taux de clic publicitaire des ressources | Clics sur les ressources/Vues des ressources | Mesure calculée | |
| taux de clic publicitaire de l’expérience | Clics sur l’expérience / Vues de l’expérience | Mesure calculée | |

{style="table-layout:fixed"}

