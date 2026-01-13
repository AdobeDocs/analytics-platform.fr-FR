---
title: Concevoir le schéma à utiliser avec Customer Journey Analytics
description: Découvrez comment concevoir un schéma XDM qui libère la flexibilité de Customer Journey Analytics, tout en prenant en charge un chemin de migration pratique à partir d’Adobe Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: b94c60c9832bc699212dda97ad634e8d3260c45c
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 9%

---

# Concevoir le schéma à utiliser avec Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Concevoir un schéma"
>abstract="Au sein de votre organisation, discutez des exigences de la collecte de données et déterminez comment vous souhaitez créer un schéma à utiliser dans Adobe Experience Platform. Cette étape s’affiche, car vous souhaitez utiliser le processus recommandé d’utilisation d’un schéma adapté à votre organisation. Il est essentiel d’effectuer cette étape correctement, car un schéma sur lequel toutes les équipes de votre organisation s’alignent facilite considérablement l’ingestion des données.<br><br>Le temps estimé nécessaire pour rassembler toutes les parties concernées au sein de votre organisation afin de s’aligner sur un schéma unifié est de 1 à 2 mois. Cette période dépend fortement du nombre d’équipes à coordonner et du nombre de dimensions et de mesures sur lesquelles s’aligner."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe recommande de créer un schéma [Modèle de données d’expérience](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home) (XDM) personnalisé pour Customer Journey Analytics lors de l’implémentation de la [collecte de données Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/collection/home). La création de ce schéma est généralement effectuée avant toute modification d’implémentation ou modification de code. Un schéma personnalisé vous permet de concevoir un contrat de données concis et spécifique à une organisation, sans hériter des contraintes d’Adobe Analytics. Voir [Choisir votre schéma pour Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) pour en savoir plus sur les types de schémas disponibles pour votre organisation.

Les schémas sont destinés à être des versions optimisées de la manière dont vous souhaitez que vos données soient structurées à long terme. Les modifications apportées aux schémas sont coûteuses car elles ont un impact sur la collecte de données, la validation et les services en aval. Vous pouvez ajouter des éléments aux schémas au fil du temps en fonction des besoins de l’entreprise. Toutefois, les champs de schéma ne peuvent pas être supprimés une fois que les données commencent à y circuler.

## Comparaison des schémas aux vues de données

Le pipeline de données pour Customer Journey Analytics contient des zones distinctes pour la collecte et l’interprétation des données. Lors de la mise à niveau à partir d’Adobe Analytics, une erreur courante est d’essayer de recréer des props et des eVars avec leurs comportements dans XDM. Utilisez plutôt le SDK Web pour collecter les données et utiliser [Vues de données](/help/data-views/data-views.md) pour déterminer comment ces données sont interprétées dans les rapports.

| Calque | objectif du Principal | Flexibilité | Ce qui appartient | Ce qui n’appartient pas |
|---|---|---|---|
| **Schéma XDM** | Définir la structure et la signification durables des données collectées | Rigide ; considéré comme des points de données immuables | Forme Événement et entité, signification du champ, relations, valeurs autorisées, réutilisation sur plusieurs canaux | « emplacements » numérotés (eVar1/prop1), logique d’attribution/de persistance, solutions de contournement spécifiques aux rapports |
| **Vues de données** | Définir le comportement des données collectées dans l’analyse | Flexible ; peut être modifié librement et peut réinterpréter les données de manière rétroactive | Paramètres des composants, comportement d’attribution et de persistance, champs dérivés, mesures filtrées, mesures calculées | Signification fondamentale des champs ; cette signification doit être stable dans le schéma. |

## Comparaison des schémas à la collecte de données Adobe Analytics

Le modèle de données d’expérience utilisé par Customer Journey Analytics offre une flexibilité bien plus grande que la plupart des autres solutions Analytics (y compris Adobe Analytics). L’établissement d’un schéma solide est l’occasion pour votre organisation d’éviter de reporter des contraintes qui existent dans d’autres produits Analytics.

| Habitude Adobe Analytics courante | Meilleure approche dans XDM + Customer Journey Analytics |
|---|---|
| Conception autour d&#39;emplacements numérotés (`eVar1`-`eVar250`, `prop1`-`prop75`) | Créez des champs à la signification stable (par exemple, `search.term`, `content.category`, `user.membershipTier`) et réutilisez-les de manière cohérente |
| Codage de la persistance/affectation/expiration dans le modèle de données | Capturer des faits durables dans le schéma ; appliquer un comportement d’attribution et de persistance au niveau de la vue de données |
| Duplication de la même valeur dans plusieurs variables pour obtenir des comportements de reporting | Stockez la valeur une fois et créez plusieurs composants (dimensions/mesures) à partir de celle-ci dans les vues de données |
| Création d’un « champ de mesure » unique pour chaque comptage souhaité | Capturez les bons faits une fois (souvent sous forme d’énumérations/booléens/chaînes), puis définissez des mesures sous forme de nombres filtrés dans les vues de données |
| Concevoir des variables pour la création de rapports « prérésolus » | Concevez votre schéma pour capturer des faits et utiliser des vues de données pour résoudre la sémantique des rapports |

## Établissement d’un schéma à l’aide d’attributs communs

Un schéma unifié sur plusieurs canaux devient possible lorsque vous normalisez un ensemble d’attributs réutilisables qui apparaissent sur de nombreux événements. Voici quelques exemples :

* **Contexte d’expérience :** nom du site/de l’application, environnement, paramètre régional, canal, marque
* **contexte de Parcours :** identifiants de campagne, contexte référent, identifiants d’expérience
* **État utilisateur :** état de connexion, niveau d’abonnement, type de compte
* **Détails de l’interaction :** nom/type de l’interaction, zone géographique de l’interface utilisateur, libellé de l’élément, catégorie d’erreur

La clé consiste à normaliser ce que le champ représente, quel que soit le canal. Évitez de modéliser le même concept différemment sur l’ensemble des canaux, à moins qu’ils ne représentent réellement des concepts différents. Par exemple, il peut être judicieux d’éviter de disposer de champs de schéma distincts pour les identifiants de campagne web et de campagne mobile. Des champs de schéma distincts rendent plus difficile l’établissement d’un retour cross-canal sur les données de dépenses publicitaires. Si une distinction est requise dans les rapports, vous pouvez segmenter par canal ou concaténer plusieurs champs pour fournir cette distinction. Le même champ de schéma peut être utilisé dans un nombre indéfini de dimensions ou de mesures.

Un moyen pratique de prendre en charge plusieurs canaux tout en conservant une stratégie de schéma unique consiste à utiliser un modèle **core + extensions** :

* **Core :** champs qui s’appliquent largement aux canaux et aux équipes
* **Extensions :** groupes de champs spécifiques à un canal ou à un domaine qui s’appliquent uniquement lorsque cela est nécessaire (interaction web, commerce, cycle de vie mobile, détails côté serveur)

Ce modèle prend en charge une stratégie de schéma organisationnel unique sans forcer les équipes à remplir des champs inutiles.

## Préférez les groupes de champs standard lorsqu’ils correspondent.

Adobe recommande d’utiliser des groupes de champs normalisés lorsqu’ils correspondent à vos besoins et d’utiliser des champs personnalisés pour les concepts spécifiques à une organisation.

Les groupes de champs standard vous aident généralement à :

* Réduire l’ambiguïté en utilisant la sémantique de champ connue
* Alignement plus facile entre les équipes
* Prise en charge de l’interopérabilité entre les applications Adobe Experience Platform

Les champs personnalisés sont appropriés dans les cas suivants :

* Votre organisation applique des concepts qui ne correspondent pas clairement aux champs standard
* Vous avez besoin d’attributs supplémentaires pour répondre aux exigences de reporting, de gouvernance ou d’activation
* Vous souhaitez représenter une taxonomie spécifique à l’entreprise (par exemple, des catégories de contenu interne)

## Déterminer comment les mesures sont comptabilisées

Dans Adobe Analytics, de nombreuses équipes considèrent la variable `events` comme le seul moyen d’effectuer le suivi des mesures. Dans Customer Journey Analytics, vous pouvez effectuer le suivi des mesures de plusieurs manières en fonction de ce que vous devez compter et de la manière dont vous souhaitez l’interpréter.

Lors de l’architecture d’un schéma, tenez compte des faits. Par exemple, `error.type = "validation"`, `user.isLoggedIn = true`, `checkout.step = "shipping"`. Définissez les mesures dans la vue de données sous la forme de nombres et de nombres filtrés sur ces faits. Par exemple :

* `checkout.step` (énumération/chaîne) peut alimenter :
   * « Passage en caisse : étape d’expédition atteinte » (nombre où `checkout.step == "shipping"`)
   * « Passage en caisse : étape de paiement atteinte »
* `error.type` (énumération/chaîne) peut alimenter :
   * « Erreurs de validation »
   * « Erreurs d’autorisation »
* `user.isLoggedIn` (booléen) peut alimenter :
   * « Sessions authentifiées »
   * « Conversions authentifiées »

>[!TIP]
>
>Lorsque vous décidez ultérieurement si un élément doit être un champ dédié dans le schéma plutôt qu’un champ dérivé, préférez la capture du fait durable dans le schéma s’il est largement utile et stable. Vous pouvez utiliser des champs dérivés pour corriger ou remodeler les données après leur collecte.

## Maintenir la parité avec Adobe Analytics pendant la transition sans encombrement des schémas

Certaines organisations doivent continuer à générer des rapports Adobe Analytics lors de la mise à niveau vers Customer Journey Analytics. Vous pouvez maintenir la parité sans introduire d’artefacts spécifiques d’Analytics dans votre conception de schéma à long terme à l’aide de l’approche suivante :

1. **Utiliser des chemins d’accès aux champs XDM reconnus et automatiquement mappés par Adobe Analytics :** lorsque vous envoyez des champs XDM reconnus par Edge Network à Adobe Analytics, ils sont [&#x200B; mappés automatiquement](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/xdm-var-mapping) sans configuration supplémentaire.
1. **Utiliser des champs XDM personnalisés pour les concepts spécifiques à une organisation :** tous les champs XDM qui ne sont pas automatiquement mappés à une variable Analytics sont transférés en tant que [variables de données contextuelles](https://experienceleague.adobe.com/fr/docs/analytics/implementation/vars/page-vars/contextdata) dans Adobe Analytics.
1. **Utilisez les règles de traitement Adobe Analytics pour mapper ces variables de données contextuelles aux props/eVars:** [règles de traitement](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview) pour vous permettre de mapper n’importe quel champ XDM personnalisé dans n’importe quelle eVar ou prop. Ce concept prend en charge le reporting de parité dans Adobe Analytics tout en gardant votre schéma propre et centré sur Customer Journey Analytics.

## Identifier les parties prenantes et définir la propriété

La conception du schéma réussit lorsque la signification du champ est convenue et conservée. Bien que les structures organisationnelles varient, les rôles suivants y participent généralement :

* **Administrateur/analyste Analytics** : définit les questions de reporting, vérifie que les champs représentent des concepts significatifs et examine la sémantique de l’analyse dans les vues de données.
* **Développeur/propriétaire de l’implémentation** : s’assure que les champs peuvent être collectés de manière fiable à l’aide du SDK web et qu’ils s’alignent sur la couche de données/l’instrumentation de l’application.
* **Architecte/ingénieur de données** : garantit la cohérence des schémas, la réutilisation sur plusieurs domaines et la compatibilité avec les services en aval.
* **Partie prenante en charge de la confidentialité/gouvernance** : examine la minimisation des données, les attentes en matière de consentement et les contraintes d’utilisation des données.

Définissez un propriétaire clair pour les modifications de schéma. Un schéma stable avec un contrôle des modifications discipliné empêche les ruptures en aval et réduit les reprises. Envisagez d’utiliser un workflow ou un outil de gouvernance du suivi pour démocratiser les requêtes et gérer le contrôle des modifications au fil du temps.

## Considérations relatives à la confidentialité et à la gouvernance

La conception du schéma doit refléter les attentes en matière de confidentialité et de gouvernance, conformément aux politiques de confidentialité de votre organisation. Tenez compte des points suivants lors de la conception de votre schéma :

* Collectez uniquement les éléments nécessaires pour prendre en charge les cas d’utilisation définis.
* Assurez-vous que les exigences en matière de consentement et d’utilisation des données sont prises en compte dans votre stratégie de collecte. Pour plus d’informations[&#x200B; voir &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/consent/sdk) Utilisation de Web SDK pour traiter les données de consentement client.
* Tenez compte de la manière dont les champs sensibles sont étiquetés et contrôlés dans les outils de gouvernance de Adobe Experience Platform. Voir [Adobe Customer Journey Analytics et gouvernance des données](/help/privacy/privacy-overview.md) pour plus d’informations.

## Étapes suivantes

Une fois que vous avez établi et accepté une architecture de schéma, vous pouvez commencer à la créer dans Adobe Experience Platform. Voir [Création d’un schéma personnalisé à utiliser avec Customer Journey Analytics](cja-upgrade-schema-create.md) pour plus d’informations.
