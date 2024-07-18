---
title: Adresses IP utilisées par le Customer Journey Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
solution: Customer Journey Analytics
feature: Basics
exl-id: 5c52986c-7ff3-45b5-9039-2bfb6529238c
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 33%

---

# Adresses IP utilisées par le Customer Journey Analytics

Certaines configurations de pare-feu bloquent les adresses IP en provenance des serveurs de collecte de données d’Adobe ou des serveurs responsables de l’accès aux données. Vous pouvez utiliser cette liste de plages pour modifier les paramètres de pare-feu de votre entreprise afin d’autoriser l’accès et d’envoyer des données depuis votre entreprise.

Cette page comprend les adresses ip que vous devez ajouter à votre liste autorisée pour que les systèmes sortants fonctionnent, comme [l’exportation de données vers un fournisseur cloud](/help/analysis-workspace/export/export-cloud.md).

>[!IMPORTANT]
>
>Bien qu’Adobe fasse de son mieux pour garder ce document à jour, il ne peut garantir que la liste des plages d’adresses IP reste la même. Les modifications possibles comprennent la croissance et l’expansion de l’entreprise, un registre Internet nécessite des modifications de l’espace d’adresse IP de l’Adobe ou un fournisseur de services Internet cesse de fonctionner.

## VA7 : clients des États-Unis et des Amériques

| Bloc IP (notation CIDR) |
| --- |
| `52.254.106.192/28` |
| `52.254.107.80/28` |
| `52.254.106.240/28` |
| `52.254.107.32/28` |
| `52.254.106.176/28` |
| `52.254.106.144/28` |
| `52.254.107.64/28` |
| `20.186.185.181` |
| `20.186.185.239` |
| `52.254.106.160/28` |
| `40.70.154.136/29` |
| `20.22.83.112` |
| `52.254.107.16/28` |
| `52.254.105.192/28` |
| `52.254.107.144/28` |
| `52.254.106.0/28` |
| `52.254.106.224/28` |
| `52.254.107.128/28` |
| `52.254.106.208/28` |
| `20.186.185.227` |
| `52.254.107.0/28` |

## NLD2 : Europe

| Bloc IP (notation CIDR) |
| --- |
| `40.74.6.128/28` |
| `51.144.184.248/29` |
| `40.74.7.192/28` |
| `40.74.7.128/28` |
| `40.74.7.176/28` |
| `20.50.23.153` |
| `40.74.6.80/28` |
| `40.74.6.144/28` |
| `40.74.5.128/28` |
| `51.105.144.1` |
| `51.105.144.81` |
| `40.74.4.176/28` |
| `52.142.236.87` |
| `40.74.4.144/28` |
| `20.101.246.9` |
| `40.74.4.160/28` |
| `40.74.7.160/28` |
| `40.74.7.144/28` |
| `40.74.3.176/28` |
| `51.124.70.4` |
| `40.74.6.96/28` |
| `40.74.7.208/28` |
| `40.74.6.112/28` |

## AUS5 : Australie

| Bloc IP (notation CIDR) |
| --- |
| `20.43.110.192/28` |
| `20.40.185.111` |
| `20.43.97.95` |
| `20.43.111.16/28` |
| `20.193.38.208/28` |
| `20.43.110.64/28` |
| `20.40.185.225` |
| `20.43.110.112/28` |
| `20.43.110.224/28` |
| `20.193.36.37` |
| `20.43.110.240/28` |
| `20.43.111.32/28` |
| `20.40.185.185` |
| `20.43.111.0/28` |
| `20.43.110.208/28` |
| `20.43.110.96/28` |
| `20.43.110.48/28` |
| `20.43.110.128/28` |
| `20.43.110.160/28` |
| `20.43.110.80/28` |
| `20.193.56.144/28` |
| `20.193.56.160/28` |
| `20.43.110.176/28` |
| `20.43.110.144/28` |
| `20.53.111.113` |
| `20.193.56.128/28` |
| `20.227.32.175` |

## CAN2 : Canada

| Bloc IP (notation CIDR) |
| --- |
| `20.116.159.80/28` |
| `20.116.159.224/28` |
| `20.116.159.192/28` |
| `20.116.159.64/28` |
| `20.151.241.173` |
| `20.116.159.128/28` |
| `20.116.159.208/28` |
| `20.116.159.48/28` |
| `20.151.240.247` |
| `20.116.159.0/28` |
| `20.220.243.238` |
| `20.116.175.240/28` |
| `20.116.155.128/28` |
| `20.116.248.0/28` |
| `20.151.241.138` |
| `20.116.159.144/28` |
| `20.116.175.224/28` |
| `20.116.248.16/28` |
| `20.151.241.124` |
| `20.116.159.160/28` |
| `20.116.159.96/28` |
| `20.104.5.248` |
| `20.116.159.112/28` |
| `20.116.159.176/28` |
| `20.116.159.32/28` |
| `20.116.158.240/28` |

>[!MORELIKETHIS]
>
>[Domaines utilisés par Customer Journey Analytics](domains.md)
>
>[Adresses IP utilisées par Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)