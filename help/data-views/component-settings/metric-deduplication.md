---
title: Paramètres du composant de déduplication des mesures
description: Ne comptabilise que la première occurrence d’une mesure dans les rapports.
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 9%

---


# Paramètres du composant de déduplication des mesures

La déduplication des mesures vous permet de configurer une mesure pour qu’elle comptabilise uniquement les valeurs de manière non répétitive.

| Paramètre | Description |
| --- | --- |
| Déduplication des mesures | Case à cocher qui vous permet d’activer le dédoublonnage des mesures. Option désactivée par défaut. |
| Portée de la déduplication | Permet de déterminer le délai de vérification unique.<br>**Session** : Seule la première occurrence de mesure de la session est comptabilisée.<br>**Personne** : Seule la première occurrence de mesure dans la fenêtre de création de rapports est comptabilisée. |
| ID de la déduplication | Au lieu d’appliquer la déduplication sur la mesure elle-même, vous permet d’appliquer la déduplication des mesures en fonction d’une dimension à la place. Utile pour les dimensions telles que l’identifiant d’achat pour appliquer la déduplication. |
