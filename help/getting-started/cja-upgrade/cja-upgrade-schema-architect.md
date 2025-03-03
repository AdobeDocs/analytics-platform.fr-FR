---
title: Concevoir le schéma à utiliser avec Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 28%

---

# Concevoir le schéma à utiliser avec Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Concevoir un schéma"
>abstract="Au sein de votre organisation, discutez des exigences de la collecte de données et déterminez comment vous souhaitez créer un schéma à utiliser dans Adobe Experience Platform. Cette étape s’affiche, car vous souhaitez utiliser le processus recommandé d’utilisation d’un schéma adapté à votre organisation. Il est essentiel d’effectuer cette étape correctement, car un schéma sur lequel toutes les équipes de votre organisation s’alignent facilite considérablement l’ingestion des données.<br><br>Le temps estimé nécessaire pour rassembler toutes les parties concernées au sein de votre organisation afin de s’aligner sur un schéma unifié est de 1 à 2 mois. Cette période dépend fortement du nombre d’équipes à coordonner et du nombre de dimensions et de mesures sur lesquelles s’aligner."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe recommande de créer un schéma de modèle de données d’expérience (XDM) personnalisé à utiliser avec le SDK Web lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics. Vous pouvez également utiliser le schéma Adobe Analytics par défaut, qui utilise le groupe de champs ExperienceEvent d’Adobe Analytics .

Un schéma XDM personnalisé permet d’obtenir un schéma simplifié adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez. Contrairement au schéma Adobe Analytics par défaut qui utilise le groupe de champs Adobe Analytics ExperienceEvent, lorsque des modifications apportées à un schéma XDM personnalisé sont requises, vous n’avez pas à passer au crible des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.

Pour plus d’informations sur ces options de schéma, voir [Choisir le schéma pour Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Consultez les sections suivantes lorsque vous commencez à architecturer votre schéma XDM.

## Évitez les restrictions Adobe Analytics dans votre schéma XDM

L’architecture sous-jacente de Customer Journey Analytics offre beaucoup plus de flexibilité qu’Adobe Analytics. La création d’un schéma XDM est un moyen essentiel de déverrouiller cette flexibilité. Lors de la mise à niveau vers Customer Journey Analytics, veillez à ne pas transférer les restrictions Adobe Analytics inutiles dans votre schéma.

| Architecture des données Adobe Analytics | Architecture du schéma XDM |
|---------|----------|
| Des mesures individuelles sont ajoutées à l’architecture des données Analytics.<br/>Par exemple, dans Adobe Analytics, vous disposez d’une eVar différente pour chaque événement. | Créer des mesures individuelles dans la vue de données plutôt que dans le schéma XDM. Vous bénéficiez ainsi d’une plus grande flexibilité dans si vous devez apporter des modifications ultérieurement.<br/>Par exemple, dans Customer Journey Analytics, vous n’avez qu’un seul événement dans le schéma, et vous utilisez créer des événements dans la vue de données. |
| Les props et les eVars sont nécessaires pour créer des variables personnalisées. | B2 |
| A3 | B3 |

## Identification de votre équipe de données et des autres parties prenantes dans l’ensemble de votre organisation


## Prenez en compte les autres applications Adobe Experience Platform utilisées dans votre organisation



1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
