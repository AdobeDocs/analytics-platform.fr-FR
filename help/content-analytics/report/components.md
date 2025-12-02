---
title: Composants de Content Analytics
description: Détails sur les composants Content Analytics spécifiques, tels que les dimensions, les mesures (calculées) et les champs dérivés.
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 100%

---

# Composants de Content Analytics

Content Analytics ajoute les catégories de composants suivantes (dimensions, mesures (calculées), champs dérivés) aux composants déjà disponibles dans Customer Journey Analytics :

* [Métadonnées de l’expérience](#experience-metadata)
* [Attributs de l’expérience](#experience-attributes)
* [Événements de l’expérience](#experience-events)
* [Métadonnées de la ressource](#asset-metadata)
* [Attributs de la ressource](#asset-attributes)
* [Événements des ressources](#asset-events)
* [Mesures calculées](#calculated-metrics)

Dans les tableaux ci-dessous, ![généré par l’IA](/help/assets/icons/AI.svg) indique une paire attribut/valeur générée par l’IA ou le machine learning.

## Métadonnées de l’expérience

| Titre | Description | Type |
|---|---|---|
| Canal d’expérience | Canal de l’expérience. | Dimension |
| ID d’expérience | ID unique de l’expérience. | Dimension |
| URL de miniature de l’expérience | URL de la miniature de l’expérience. | Dimension |
| Profondeur horizontale de l’expérience en pourcentage | Valeur quantifiable de la profondeur horizontale en pourcentage de l’expérience. | Dimension<br/>Champ dérivé |
| Profondeur verticale de l’expérience en pourcentage | Valeur quantifiable de la profondeur verticale en pourcentage de l’expérience. | Dimension<br/>Champ dérivé |

{style="table-layout:fixed"}



## Attributs de l’expérience

| Titre | Description | Type |
|---|---|---|
| Attributs de l’expérience | ![Générés par l’IA](/help/assets/icons/AI.svg) Liste complète de tous les noms et valeurs d’attribut de l’expérience. | Dimension<br>Champ dérivé |
| Score de lisibilité de l’expérience | ![Généré par l’IA](/help/assets/icons/AI.svg) Score de lisibilité de l’expérience. | Dimension |
| Mots-clés de l’expérience | ![Générés par l’IA](/help/assets/icons/AI.svg) Mots-clés pour l’expérience. | Dimension<br>Champ dérivé |
| Stratégies de persuasion de l’expérience | ![Générées par l’IA](/help/assets/icons/AI.svg) Stratégies de persuasion contenues dans l’expérience donnée. Les valeurs possibles sont : identité sociale, preuve sociale, autorité, concret, phénomène du premier pas, dépasser la réactance, réciprocité, ancrage et comparaison, impact social, rareté et anthropomorphisme. | Dimension<br/>Champ dérivé |
| Narrations de l’expérience | ![Générées par l’IA](/help/assets/icons/AI.svg) Récits que l’expérience crée en fonction de la pertinence du point de vue d’un spécialiste marketing. | Dimension<br/>Champ dérivé |
| Tons de l’expérience | ![Générés par l’IA](/help/assets/icons/AI.svg) Tons que l’expérience crée en fonction de la pertinence du point de vue d’un spécialiste marketing. | Dimension<br/>Champ dérivé |
| Émotions marketing de l’expérience | ![Générées par l’IA](/help/assets/icons/AI.svg) Les émotions suscitées chez le lecteur lors de la lecture du texte utilisé dans le cadre de l’expérience : urgence, exclusivité, encouragement, défi, curiosité, accomplissement, confiance, simplicité et fascination. | Dimension<br/>Champ dérivé |
| Nombre d’émoticônes de l’expérience | ![Généré par l’IA](/help/assets/icons/AI.svg) Nombre d’émoticônes pour l’expérience. | Mesure |
| Nombre de hashtags de l’expérience | ![Généré par l’IA](/help/assets/icons/AI.svg) Nombre de hashtags pour l’expérience. | Mesure |
| Nombre de phrases de l’expérience | ![Généré par l’IA](/help/assets/icons/AI.svg) Nombre de phrases pour l’expérience. | Mesure |
| Taux de mots vides de l’expérience | ![Généré par l’IA](/help/assets/icons/AI.svg) Nombre de mots vides pour l’expérience. | Mesure |
| Nombre de citations de texte de l’expérience | ![Généré par l’IA](/help/assets/icons/AI.svg) Nombre de citations textuelles pour l’expérience. | Mesure |
| Nombre de mots de l’expérience | ![Généré par l’IA](/help/assets/icons/AI.svg) Nombre de mots pour l’expérience. | Mesure |
| Nombre de mots de l’expérience par phrase | ![Généré par l’IA](/help/assets/icons/AI.svg) Nombre de mots par phrases pour l’expérience. | Mesure |

{style="table-layout:fixed"}


## Événements de l’expérience

| Titre | Description | Type |
|---|---|---|
| Vues de l’expérience | Mesure quantifiable du nombre de vues de l’expérience. | Mesure |
| Clics de l’expérience | Mesure quantifiable du nombre de clics de l’expérience. | Mesure |

{style="table-layout:fixed"}


## Métadonnées de la ressource

| Titre | Description | Type |
|---|---|---|
| ID de ressource | Identifiant unique de la ressource. Le binaire de la ressource détermine son unicité. Si le binaire de la ressource change, l’identifiant change. L’ID unique peut être l’URL, mais il peut également s’agir d’un hachage créé. | Dimension |
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
| Attributs de la ressource | ![Générés par l’IA](/help/assets/icons/AI.svg) Liste complète de tous les noms et valeurs d’attributs de ressources. | Dimension<br>Champ dérivé |
| Orientation de la ressource | ![Générée par l’IA](/help/assets/icons/AI.svg) Orientation de la ressource. | Dimension<br/>Champ dérivé |
| Ton général de la ressource | ![Généré par l’IA](/help/assets/icons/AI.svg) Ton global de la ressource. | Dimension<br/>Champ dérivé |
| Couleurs du premier plan de la ressource | ![Générées par l’IA](/help/assets/icons/AI.svg) Couleurs du premier plan de la ressource. | Dimension<br/>Champ dérivé |
| Couleurs de l’arrière-plan de la ressource | ![Générées par l’IA](/help/assets/icons/AI.svg) Couleurs de l’arrière-plan de la ressource. | Dimension<br/>Champ dérivé |
| Balises de la ressource | ![Générées par l’IA](/help/assets/icons/AI.svg) Balises de la ressource. | Dimension<br/>Champ dérivé |
| Scènes de ressource | ![Générées par l’IA](/help/assets/icons/AI.svg) Scènes pour la ressource. | Dimension<br/>Champ dérivé |
| Objets de la ressource | ![Générés par l’IA](/help/assets/icons/AI.svg) Objets de la ressource. | Dimension<br/>Champ dérivé |
| Styles de photographie de la ressource | ![Générés par l’IA](/help/assets/icons/AI.svg) Styles de photographie de la ressource. | Dimension<br/>Champ dérivé |
| Type d’image de la ressource | ![Généré par l’IA](/help/assets/icons/AI.svg) Type d’image de la ressource. Les valeurs possibles sont les suivantes : photographie, schéma, peinture, dessin numérique, infographie, design graphique, collage et capture d’écran du logiciel. | Dimension<br/>Champ dérivé |
| Positions des caméras de la ressource | ![Générées par l’IA](/help/assets/icons/AI.svg) Positions des caméras de la ressource. | Dimension<br/>Champ dérivé |
| Proximités des caméras de la ressource | ![Générées par l’IA](/help/assets/icons/AI.svg) Proximités des caméras de la ressource. | Dimension<br/>Champ dérivé |
| Catégories de personnes de la ressource | ![Générées par l’IA](/help/assets/icons/AI.svg) Catégories de personnes de la ressource. Les valeurs possibles sont : personne, homme, femme, groupe social, foule, personnes, garçon, fille et enfant. | Dimension<br/>Champ dérivé |
| Densité du contenu visuel de la ressource | ![Générée par l’IA](/help/assets/icons/AI.svg) Densité du contenu visuel de la ressource. Les valeurs possibles sont : faible, moyenne ou élevée. Une faible densité de contenu implique une petite quantité d’informations présentes par zone unitaire de l’image. | Dimension |
| Diffusion d’attention visuelle de la ressource | ![Générée par l’IA](/help/assets/icons/AI.svg) Diffusion d’attention visuelle de la ressource. Les valeurs possibles sont : faible, moyenne ou élevée. La diffusion de l’attention fait référence à la mesure dans laquelle l’attention d’un observateur ou d’une observatrice est divisée entre différentes parties d’une image. | Dimension<br/>Champ dérivé |
| Condition d’éclairage de la ressource | ![Générée par l’IA](/help/assets/icons/AI.svg) Condition d’éclairage de la ressource. Les valeurs possibles sont : heure dorée, heure bleue, midi, ciel couvert, nuit, haute lumière, faible lumière, lumière du jour, incandescent, fluorescent, coloré et studio. | Dimension<br/>Champ dérivé |
| Paramètres de la caméra de la ressource | ![Générés par l’IA](/help/assets/icons/AI.svg) Paramètres de la caméra de la ressource. Les valeurs possibles sont : vitesse d’obturation rapide, exposition longue, flou bokeh, flou directionnel, flou avec bascule et décentrement, flash, grand angle, noir et blanc, surréaliste, double exposition, macro et mode normal. | Dimension<br/>Champ dérivé |

{style="table-layout:fixed"}


## Événements de la ressource

| Titre | Description | Type |
|---|---|---|
| Vues de la ressource | Mesure quantifiable du nombre de vues de la ressource. | Mesure |
| Clics sur la ressource | Mesure quantifiable du nombre de clics sur la ressource. | Mesure |

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
| Taux de clic publicitaire sur la ressource | Clics sur la ressource/Vues de la ressource | Mesure calculée |
| Taux de clic publicitaire sur l’expérience | Clics sur l’expérience/Vues de l’expérience | Mesure calculée |

{style="table-layout:fixed"}

