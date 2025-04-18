---
title: Concepts et fonctionnalités de Customer Journey Analytics B2B edition
description: Concepts et fonctions de B2B edition de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# Concepts et fonctions de B2B edition

{{draft-b2b}}

Cet article explique les concepts généraux et les fonctionnalités des jeux de données et des conteneurs, ainsi que les différences entre la norme et le B2B edition de Customer Journey Analytics.

Les jeux de données sont les sources d’une connexion. Lors de la configuration d’une connexion, vous définissez des jeux de données qui feront partie de cette connexion.

Les conteneurs sont utilisés dans Customer Journey Analytics pour prendre en charge et faciliter des fonctionnalités telles que les segments, les mesures calculées et les fonctionnalités d’analyse avancées.




## Conteneurs standard

La version *standard* de Customer Journey Analytics repose sur le concept de trois conteneurs : Personne, Session et Événement. Dans une configuration Customer Journey Analytics standard, ces conteneurs pertinents sont générés implicitement en fonction de votre configuration.

Vous pouvez redéfinir la manière dont ces conteneurs sont nommés lorsque vous configurez une vue de données, mais conceptuellement, la version standard utilise une hiérarchie de conteneurs basée sur les personnes.

![B2C](assets/b2c-containers.svg){zoomable="yes"}

Dans la connexion, vous ajoutez des jeux de données d’événement, de profil et de recherche, puis vous sélectionnez des identités à utiliser pour définir la connexion entre ces jeux de données. Dans le cadre de la connexion, une hiérarchie de conteneurs basée sur les personnes est générée automatiquement. Dans cette hiérarchie, le conteneur de sessions est défini par les [paramètres de session](/help/data-views/session-settings.md) dans votre vue de données.


## Conteneurs B2B

Dans Customer Journey Analytics B2B edition, un conteneur Compte est ajouté à la liste des conteneurs générés.  Vous avez également la possibilité de configurer la génération de conteneurs supplémentaires, tels que Compte global, Groupe d’achats et Opportunité.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

Dans la connexion, vous ajoutez des jeux de données d’événement, de compte, de compte global, d’opportunité, de groupe d’achats et d’autres jeux de données de recherche. Vous sélectionnez Compte comme identifiant principal de la connexion afin de pouvoir utiliser des identités de compte pour définir la connexion entre les jeux de données. Dans le cadre de la connexion, une hiérarchie de conteneurs basée sur les comptes est générée automatiquement. Dans cette hiérarchie, le conteneur de sessions entre le conteneur de personnes et le conteneur d’événements est défini par les [paramètres de session](/help/data-views/session-settings.md) dans votre vue de données. En outre, les conteneurs Session, par exemple entre Compte et Événement, ne sont actuellement pas pris en charge.

L’opportunité, le groupe d’achats et la personne sont tous des conteneurs frères du conteneur Compte . Consultez le tableau ci-dessous pour une description et une utilisation de base.

| Conteneur B2B | Description<br/>Cas d’utilisation de base |
|---|---|
| Compte | Une entreprise qui est un client ou un client potentiel de votre entreprise. Il peut s’agir d’une filiale ou d’une division d’une organisation plus grande. Le compte représente l&#39;organisation à laquelle vous vendez et que vous souhaitez suivre au niveau de cette organisation. |
| Compte global (facultatif) | Société mère principale d&#39;un groupe de sociétés liées. Un compte global n&#39;a pas de société mère, mais peut avoir des filiales ou des divisions appartenant au compte global. Un compte qui n’a pas de parent ou de filiale doit être répertorié à la fois dans le champ compte et dans le champ compte global, si les deux sont activés dans le cadre de la configuration d’une connexion. |
| Opportunité (facultatif) | Ensemble de produits et de services qui sont vendus ensemble. Une opportunité impliquait souvent différentes étapes du cycle de vente pour se conclure en tant que vente.<br>Vous utiliseriez les données d’opportunité pour mesurer la progression de l’opportunité via l’entonnoir de ventes. Par exemple, un rapport qui fournit des détails sur les principales opportunités qui sont passées de l’étape 3 à l’étape 4. |
| Groupe d&#39;achat (facultatif) | Ensemble de personnes au sein d’une organisation qui participent au processus de prise de décision pour l’achat d’un produit ou d’un service. <br/>Vous pouvez utiliser les données des groupes d&#39;achats pour effectuer le suivi des groupes d&#39;achats via la gestion de campagnes. Par exemple, créez un segment d’audience de groupes d’achats clés.<br/> Vous souhaitez très probablement effectuer une recherche à partir du groupe d&#39;achat dans les données de profil, afin de pouvoir créer des rapports sur les personnes d&#39;un groupe d&#39;achat. |
| Personne | Personne, souvent identifiée par une adresse e-mail unique, qui a interagi avec l’entreprise. <br/>Vous pouvez utiliser les données de profil pour identifier les personnes qui travaillent pour un compte. Par exemple : ciblez toutes les personnes d’un compte qui se sont inscrites à une conférence. |


## Correspondance par conteneur ou champ

Lorsque vous définissez une connexion dans Customer Journey Analytics, vous pouvez définir pour chaque jeu de données d’enregistrement (profil ou recherche), si ce jeu de données est mis en correspondance par conteneur ou par champ.

### Correspondance par conteneur

Si un jeu de données d’enregistrement est mis en correspondance par conteneur, par exemple par groupe d’achats, le jeu de données d’enregistrement est traité comme un type de jeu de données de profil et comme un jeu de données de profil dans l’interface utilisateur.

### Correspondance par champ

Si un jeu de données d’enregistrement est mis en correspondance par champ (par exemple, Membre de la liste marketing), le jeu de données d’enregistrement est traité comme un type de jeu de données de recherche et comme un jeu de données de recherche dans l’interface utilisateur.



## Rapport sur les données basées sur les personnes et les comptes

Si vous souhaitez créer des rapports sur des conteneurs basés sur des personnes (et des identités de personne) et des conteneurs basés sur des comptes (et des identités de compte), vous devez configurer deux connexions distinctes dans Customer Journey Analytics. Une connexion où vous sélectionnez Personne comme ID de Principal et une connexion où vous sélectionnez Compte comme ID de Principal. Customer Journey Analytics ne prend pas en charge les rapports basés sur les personnes et les comptes rendus de performances à partir du même conteneur.
