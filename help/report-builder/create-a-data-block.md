---
title: Création dʼun bloc de données à lʼaide de Report Builder dans CJA
description: Décrit comment créer un bloc de données.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
source-git-commit: 188ed6c6c32db9f65f6f31cf26311ce545d9dfb7
workflow-type: ht
source-wordcount: '464'
ht-degree: 100%

---

# Création dʼun bloc de données

Un *bloc de données* est le tableau de données créé par une requête de données unique. Un classeur Report Builder peut contenir plusieurs blocs de données. Lorsque vous créez un bloc de données, vous devez dʼabord le configurer avant de le créer.

## Configuration du bloc de données

Configurez les paramètres initiaux du bloc de données : son emplacement, les vues de données et une période.

1. Cliquez sur **Créer un bloc de données**.

   ![](./assets/create_db.png)

1. Définissez lʼ&#x200B;**Emplacement du bloc de données**.

   Lʼoption relative à lʼemplacement du bloc de données définit lʼemplacement de la feuille de calcul dans laquelle Report Builder ajoute les données.

   Pour spécifier lʼemplacement du bloc de données, sélectionnez une cellule unique dans la feuille de calcul ou saisissez une adresse de cellule telle que a3, \\\$a3, a\\$3 ou sheet1!a2. La cellule spécifiée sera le coin supérieur gauche du bloc de données lors de la récupération des données.

1. Choisissez les **Vues de données**.

   Lʼoption relative aux Vues de données vous permet de choisir une vue de données dans un menu déroulant, ou de référencer une vue de données à partir dʼun emplacement de cellule.

1. Définissez la **Période**.

   Lʼoption relative à la Période vous permet de choisir une période. Les périodes peuvent être fixes ou variables. Pour plus dʼinformations sur les options relatives aux périodes, consultez la section [Sélection dʼune période](select-date-range.md).

1. Cliquez sur **Suivant**.

   ![](./assets/choose_date_data_view3.png)

   Une fois le bloc de données configuré, sélectionnez des dimensions, des mesures et des filtres pour le créer. Les onglets Dimensions, Mesures et Filtres sʼaffichent au-dessus du volet Générateur de tableaux.
<!--
    ![](./assets/image9.png)
  -->


## Création du bloc de données

Pour créer le bloc de données, sélectionnez les composants du rapport et personnalisez leur disposition.

1. Ajoutez des dimensions, des mesures et des filtres.

   Faites défiler les listes de composants ou utilisez le champ de **recherche** pour localiser les composants. Faites glisser et déposez les composants dans le volet Tableau ou double-cliquez sur le nom dʼun composant dans la liste pour lʼajouter automatiquement au volet Tableau.

   Double-cliquez sur un composant pour lʼajouter à une section par défaut du tableau.

   - Les composants de dimension sont ajoutés à la section Ligne ou Colonne si une dimension figure déjà dans les colonnes.
   - Les composants de date sont ajoutés à la section Colonne.
   - Les composants de filtre sont ajoutés à la section Filtres.

1. Organisez les éléments dans le volet Tableau pour personnaliser la disposition de votre bloc de données.

   Faites glisser et déposez des composants dans le volet Tableau pour réorganiser les composants, ou cliquez avec le bouton droit sur le nom dʼun composant et sélectionnez le choix approprié dans le menu Options.

   Lorsque vous ajoutez des composants au tableau, une prévisualisation du bloc de données sʼaffiche à lʼemplacement du bloc de données dans la feuille de calcul. La disposition de la prévisualisation du bloc de données est automatiquement mise à jour lorsque vous ajoutez, déplacez ou supprimez des éléments du tableau.

   ![](./assets/image10.png)

1. Cliquez sur **Terminer**.

   Un message de traitement sʼaffiche pendant la récupération des données Analytics.

   ![](./assets/image11.png)

   Report Builder récupère les données et affiche le bloc de données renseigné dans la feuille de calcul.

   ![](./assets/image12.png)
