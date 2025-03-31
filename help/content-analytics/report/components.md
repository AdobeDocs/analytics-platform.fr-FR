---
title: Composants de Content Analytics
description: Détails sur les composants spécifiques de Content Analytics, tels que les dimensions, les mesures (calculées) et les champs dérivés
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 0731eadd403ecb428d36492b83351aa0e696b41f
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 22%

---

# Composants de Content Analytics

{{release-limited-testing}}

Content Analytics ajoute les catégories de composants suivantes (dimensions, mesures (calculées), champs dérivés) aux composants déjà disponibles dans Customer Journey Analytics :

* [Métadonnées d’expérience](#experience-metadata)
* [Attributs de l’expérience](#experience-attributes)
* [Événements d’expérience](#experience-events)
* [Métadonnées de ressource](#asset-metadata)
* [Attributs de la ressource](#asset-attributes)
* [Événements Assets](#asset-events)
* [Mesures calculées](#calculated-metrics)

Dans les tableaux ci-dessous, ![AI généré](/help/assets/icons/AI.svg) indique une paire attribut/valeur générée par AI/ML.

## Métadonnées d’expérience

| Titre | Description | Type |
|---|---|---|
| Canal d’expérience | Canal pour l’expérience. | Dimension |
| Identifiant d’expérience | ID unique de l’expérience. | Dimension |
| URL de miniature de l’expérience | URL de la miniature de l’expérience. | Dimension |
| Profondeur horizontale de l’expérience en pourcentage | Valeur quantifiable de la profondeur horizontale en pourcentage de l’expérience. | Champ <br/> Dimension |
| Profondeur verticale de l’expérience en pourcentage | Valeur quantifiable de la profondeur verticale en pourcentage de l’expérience. | Champ <br/> Dimension |

{style="table-layout:fixed"}



## Attributs de l’expérience

| Titre | Description | Type |
|---|---|---|
| Attributs de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Liste complète de tous les noms et valeurs d’attribut d’expérience | Champ <br> Dimension |
| Score de lisibilité de l’expérience | ![Généré par l’IA](/help/assets/icons/AI.svg) Score de lisibilité de l’expérience | Dimension |
| Mots-clés de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Mots-clés pour l’expérience. | Champ <br> Dimension |
| Stratégies de persuasion de l’expérience | ![générées par l’IA](/help/assets/icons/AI.svg) Stratégies de persuasion présentes dans l’expérience donnée. Les valeurs possibles sont : l’identité sociale, la preuve sociale, l’autorité, le concret, le pied dans la porte, surmonter la réactance, la réciprocité, l’ancrage et la comparaison, l’impact social, la rareté et l’anthropomorphisme. | Champ <br/> Dimension |
| Narrations de l’expérience | ![généré par l’IA](/help/assets/icons/AI.svg) Récits que l’expérience crée en fonction de la pertinence du point de vue d’un spécialiste marketing. | Champ <br/> Dimension |
| Tons de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Tons que l’expérience crée en fonction de la pertinence du point de vue d’un spécialiste marketing | Champ <br/> Dimension |
| Émotions marketing de l’expérience | ![L’IA générée](/help/assets/icons/AI.svg) L’émotion invoquée par le lecteur à la lecture du texte utilisé dans le cadre de l’expérience : Urgence, Exclusivité, Encouragement, Défi, Curiosité, Réussite, Confiance, Simplicité et Fascination. | Champ <br/> Dimension |
| Nombre d’émoticônes de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre d’émoticônes pour l’expérience. | Mesure |
| Nombre de hashtags de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de hashtags pour l&#39;expérience. | Mesure |
| Nombre de phrases de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de phrases pour l’expérience. | Mesure |
| Taux de mots vides de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de mots vides pour l’expérience. | Mesure |
| Nombre de citations de texte de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de guillemets pour l’expérience. | Mesure |
| Nombre de mots de l’expérience | ![IA générée](/help/assets/icons/AI.svg) Nombre de mots pour l’expérience. | Mesure |
| Nombre de mots de l’expérience par phrase | ![IA générée](/help/assets/icons/AI.svg) Nombre de mots par phrase pour l’expérience. | Mesure |

{style="table-layout:fixed"}


## Événements d’expérience

| Titre | Description | Type |
|---|---|---|
| Vues de l’expérience | Mesure quantifiable du nombre de vues de l’expérience. | Mesure |
| Clics de l’expérience | Mesure quantifiable du nombre de clics de l’expérience. | Mesure |

{style="table-layout:fixed"}


## Métadonnées de ressource

| Titre | Description | Type |
|---|---|---|
| ID de ressource | Identifiant unique de la ressource. Le fichier binaire de la ressource détermine l’unicité. Si le fichier binaire de la ressource change, l’identifiant change. L’ID unique peut être l’URL, mais il peut également s’agir d’un hachage créé. | Dimension |
| Chemin HTML de la ressource | Chemin HTML concaténé pour la ressource. | Dimension |
| URL du lien de la ressource | Ancre de page la plus proche pour la ressource. | Dimension |
| Largeur d’affichage de la ressource | Largeur d’affichage de la ressource de contenu. | Dimension |
| Hauteur d’affichage de la ressource | Hauteur d’affichage de la ressource de contenu. | Dimension |
| Gauche absolue de la ressource | Gauche absolue de la ressource de contenu. | Dimension |
| Première position absolue de la ressource | Première position absolue de la ressource de contenu. | Dimension |

{style="table-layout:fixed"}


## Attributs de la ressource

| Titre | Description | Type |
|---|---|---|
| Attributs de la ressource | ![IA générée](/help/assets/icons/AI.svg) Liste complète de tous les noms et valeurs d’attributs de ressources | Champ <br> Dimension |
| Orientation de la ressource | ![IA générée](/help/assets/icons/AI.svg) Orientation de la ressource. | Champ <br/> Dimension |
| Ton général de la ressource | ![IA générée](/help/assets/icons/AI.svg) Ton global de la ressource. | Champ <br/> Dimension |
| Couleurs du premier plan de la ressource | ![IA générée](/help/assets/icons/AI.svg) Couleurs de premier plan de la ressource. | Champ <br/> Dimension |
| Couleurs de l’arrière-plan de la ressource | ![IA générée](/help/assets/icons/AI.svg) Couleurs d’arrière-plan de la ressource. | Champ <br/> Dimension |
| Balises de la ressource | ![IA générée](/help/assets/icons/AI.svg) Balises de la ressource. | Champ <br/> Dimension |
| Scènes de ressource | ![IA générée](/help/assets/icons/AI.svg) Scènes pour la ressource. | Champ <br/> Dimension |
| Objets de la ressource | ![IA générée](/help/assets/icons/AI.svg) Objets de la ressource. | Champ <br/> Dimension |
| Styles de photographie de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) Styles de photographie de la ressource. | Champ <br/> Dimension |
| Type d’image de la ressource | ![IA générée](/help/assets/icons/AI.svg) Type d’image de la ressource. Les valeurs possibles sont les suivantes : photographie, schéma, peinture, dessin animé numérique, infographie, conception graphique, collage et capture d’écran du logiciel. | Champ <br/> Dimension |
| Positions des caméras de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) positions de la caméra de la ressource. | Champ <br/> Dimension |
| Proximités des caméras de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) Proximité de la caméra de la ressource. | Champ <br/> Dimension |
| Catégories de personnes de la ressource | ![IA générée](/help/assets/icons/AI.svg) Catégories de personnes pour la ressource. Les valeurs possibles sont les suivantes : personne, homme, femme, groupe social, foule, personnes, garçon, fille et enfant. | Champ <br/> Dimension |
| Densité du contenu visuel de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) Densité de contenu visuel de la ressource. Les valeurs possibles sont : faible, moyenne ou élevée. Une faible densité de contenu implique une petite quantité d’informations présentes par unité de surface de l’image. | Dimension |
| Diffusion d’attention visuelle de la ressource | ![IA générée](/help/assets/icons/AI.svg) Répartition de l’attention visuelle de la ressource. Les valeurs possibles sont : faible, moyenne ou élevée. La dispersion de l&#39;attention fait référence à la mesure dans laquelle l&#39;attention d&#39;un spectateur est divisée entre différentes parties d&#39;une image. | Champ <br/> Dimension |
| Condition d’éclairage de la ressource | ![IA générée](/help/assets/icons/AI.svg) Condition d’éclairage de la ressource. Les valeurs possibles sont les suivantes : heure d’or, heure bleue, midi, ciel couvert, nuit, haute résolution, basse résolution, éclairage naturel, incandescent, fluorescent, coloré et studio. | Champ <br/> Dimension |
| Paramètres de la caméra de la ressource | ![généré par l’IA](/help/assets/icons/AI.svg) Paramètre de caméra de la ressource. Les valeurs possibles sont : vitesse d&#39;obturation rapide, exposition longue. flou boréal, flou animé, flou avec décalage d&#39;inclinaison, flash, grand angle, noir et blanc, surréaliste, double exposition, macro et mode normal. | Champ <br/> Dimension |

{style="table-layout:fixed"}


## Événements de ressource

| Titre | Description | Type |
|---|---|---|
| Vues de la ressource | Mesure quantifiable du nombre de vues de la ressource. | Mesure |
| Clics sur les ressources | Mesure quantifiable du nombre de clics sur la ressource. | Mesure |

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

| Titre | Description | Type |
|---|---|---|
| Taux de clic publicitaire des ressources | Clics sur les ressources/Vues des ressources | Mesure calculée |
| taux de clic publicitaire de l’expérience | Clics sur l’expérience/Vues de l’expérience | Mesure calculée |

{style="table-layout:fixed"}

