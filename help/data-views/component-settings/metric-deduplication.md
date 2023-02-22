---
title: 'Paramètres des composants : déduplication des mesures'
description: Ne comptabilise que la première occurrence dʼune mesure dans les rapports.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 9a31b1dcba4015f00dd7ae8c43b317e1c5679a2c
workflow-type: ht
source-wordcount: '282'
ht-degree: 100%

---

# Paramètres des composants : déduplication des mesures

La déduplication de la mesure vous permet de configurer une mesure pour ne compter que les valeurs de manière non répétitive.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Déduplication des mesures] | Case à cocher vous permettant dʼactiver la déduplication de la mesure. Option désactivée par défaut. |
| [!UICONTROL Portée de la déduplication] | Permet de déterminer la période sur laquelle porte le contrôle unique.<br>**Session** : seule la première occurrence de la mesure de la session est comptabilisée.<br>**Personne** : seule la première occurrence de la mesure dans la fenêtre du compte rendu des performances est comptabilisée. |
| [!UICONTROL ID de la déduplication] | Permet dʼappliquer la déduplication de la mesure en fonction dʼune dimension, et non de la mesure elle-même. Utile pour appliquer la déduplication à des dimensions telles que lʼID dʼachat. |
| [!UICONTROL Valeur à conserver] | <ul><li>**Conserver la première instance** : utilisez cette option lorsque l’instance initiale de la mesure est valide. La plus courante serait probablement une confirmation d’achat. Même si quelqu’un recharge par inadvertance la page et que nous obtenons une autre instance d’une confirmation d’achat, l’événement initial reste valide.</li><li>**Conserver la dernière instance** : utilisez cette option dans les cas où la dernière instance est plus logique à collecter. Exemple : quelqu’un met à jour son profil en ligne. Nous ne voulons compter qu’une seule de ces mises à jour par session. Cependant, cette personne peut mettre à jour son profil plusieurs fois au cours de la session. Si nous conservons la première instance, il peut y avoir des activités qui ne sont pas liées à l’événement. En ce cas, il est plus logique de conserver la dernière instance.</li></ul> |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>La déduplication à la portée d’une _personne_ est évaluée par mois complets en heure UTC. Un créneau de rapport pour un mois partiel peut ne pas afficher toutes les premières ou dernières instances, si certaines se sont produites au cours du mois complet mais en dehors des dates de création de rapports.
