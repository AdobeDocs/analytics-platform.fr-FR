---
title: Champs dérivés
description: Un champ dérivé spécifie la manipulation de l’heure de rapport des champs de schéma et/ou des composants standard par le biais d’un ensemble de fonctions et de modèles de fonction disponibles.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
exl-id: 1ba38aa6-7db4-47f8-ad3b-c5678e5a5974
badgeDerivedFields: label="New Feature" type="Positive"
source-git-commit: daa2c69a61e80fb0e38f06ecca248658595b2c3a
workflow-type: tm+mt
source-wordcount: '2987'
ht-degree: 8%

---


# Champs dérivés

{{release-limited-testing}}

Les champs dérivés sont un aspect important de la fonctionnalité de création de rapports en temps réel dans Customer Journey Analytics (CJA). Un champ dérivé vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable. Vous pouvez ensuite utiliser ce champ dérivé comme composant (mesure ou dimension) dans [Workspace](../../analysis-workspace/home.md) ou même définir plus précisément le champ dérivé en tant que composant dans [Vue des données](../data-views.md).

Les champs dérivés permettent de gagner beaucoup de temps et d’efforts, par rapport à la transformation ou à la manipulation de vos données à d’autres emplacements en dehors de CJA. Par exemple : [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr), [Distiller de données](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)ou dans vos propres processus Extract Transform Load (ETL)/Extract Load Transform (ELT).

Les champs dérivés sont définis dans [Vues des données](../data-views.md), sont basées sur un ensemble de fonctions définies en tant que règles et appliquées aux champs standard et/ou de schéma disponibles.

Voici des exemples de cas d’utilisation :

- Définissez un champ Nom de page dérivé qui corrige les valeurs de nom de page collectées incorrectes afin de corriger les valeurs de nom de page.

- Définissez un champ Canal marketing dérivé qui détermine le canal marketing approprié en fonction d’une ou de plusieurs conditions (par exemple, un paramètre d’URL, une URL de page, un nom de page).

## Interface de champ dérivée

Lorsque vous créez ou modifiez un champ dérivé, vous utilisez l’interface de champ dérivé.

![Boîte de dialogue de champ dérivé](assets/derived-field-dialog.png)


|  | Nom | Description |
|---------|----------|--------|
| 1 | **Sélecteur** | Vous utilisez la zone de sélecteur pour sélectionner et faire glisser et déposer votre ![Fonction](assets/Smock_Function_18_N.svg) fonction,![Icône Modèle de fonction](assets/Smock_FileTemplate_18_N.svg) modèle de fonction,![Icône Champ de schéma](assets/Smock_Folder_18_N.svg) champ de schéma, ou![Icône de champ standard](assets/Smock_DragHandle_18_N.svg)du champ standard au créateur de règles. <br/>Utilisez la liste déroulante pour effectuer une sélection entre les [!UICONTROL Fonctions], [!UICONTROL Modèles de fonction], [!UICONTROL Champs de schéma], et [!UICONTROL Champs standard].<br/>Vous pouvez rechercher des champs de fonction, de modèle de fonction, de schéma et standard à l’aide de la variable ![Icône Rechercher](assets/Smock_Search_18_N.svg) Zone de recherche. <br/>Vous pouvez filtrer la liste d’objets sélectionnée en sélectionnant ![Icône Filtrer](assets/Smock_Filter_18_N.svg) Filtrez et spécifiez des filtres dans la variable [!UICONTROL Filtrage des champs par] boîte de dialogue. Vous pouvez facilement supprimer des filtres à l’aide de ![Icône Fermer](assets/CrossSize75.svg) pour chaque filtre. |
| 2 | **Créateur de règles** | Vous créez votre champ dérivé de manière séquentielle à l’aide d’une ou de plusieurs règles. Une règle est une implémentation spécifique d’une fonction et est donc toujours associée à une seule fonction. Pour créer une règle, faites-la glisser et déposez-la dans le créateur de règles. Le type de fonction détermine l’interface de la règle.<br/>Voir [Interface des règles](#rule-interface) pour plus d’informations. <br/>Vous pouvez insérer une fonction au début, à la fin ou entre les règles déjà disponibles dans le créateur de règles. La dernière règle du créateur de règles détermine la sortie finale du champ dérivé. |
| 3 | **[!UICONTROL ** Paramètres des champs **]** | Vous pouvez nommer et décrire votre champ dérivé et inspecter son type de champ. |
| 4 | **[!UICONTROL ** Sortie finale **]** | Cette zone affiche un aperçu mis à jour à la volée des valeurs de sortie, en fonction des données des 30 derniers jours et des modifications apportées au champ dérivé dans le créateur de règles. |

{style="table-layout:auto"}

## Assistant de modèle de champ

Lorsque vous accédez pour la première fois à l’interface de champ dérivé, la variable [!UICONTROL Commencer avec un modèle de champ] s’affiche.

1. Sélectionnez le modèle qui décrit le mieux le type de champ que vous essayez de créer.
2. Sélectionnez la **[!UICONTROL ** Sélectionner **]** pour continuer.

La boîte de dialogue de champ dérivé est remplie avec des règles (et fonctions) requises ou utiles pour le type de champ que vous avez sélectionné. Voir [Modèles de fonction](#function-templates) pour plus d’informations sur les modèles disponibles.

## Interface des règles

Lorsque vous définissez une règle dans le créateur de règles, vous utilisez l’interface des règles.

![Interface des règles](assets/rule-interface.png)

|  | Nom | Description |
|---------|----------|--------|
| A   | **Nom de la règle** | Par défaut, le nom de la règle est **Règle X** (X faisant référence à un numéro de séquence). Pour modifier le nom d’une règle, sélectionnez son nom et saisissez-le dans le nouveau nom, par exemple `Query Parameter`. |
| B | **Nom de la fonction** | Nom de fonction sélectionné pour la règle, par exemple [!DNL URL PARSE]. Lorsque la fonction est la dernière de la séquence de fonctions et qu’elle détermine les valeurs de sortie finales, le nom de la fonction est suivi de [!DNL - FINAL OUTPUT], par exemple [!DNL URL PARSE - FINAL OUTPUT]. <br/>Pour afficher une fenêtre contextuelle contenant plus d’informations sur la fonction, sélectionnez ![Icône Aide](assets/Smock_HelpOutline_18_N.svg). |
| C   | **Description de la règle** | Vous pouvez éventuellement ajouter une description à une règle.<br/>Sélectionner ![Icône Plus](assets/More.svg), puis sélectionnez **[!UICONTROL ** Ajouter une description **]** pour ajouter une description ou **[!UICONTROL ** Modifier la description **]** pour modifier une description existante.<br/>Utilisez l’éditeur pour saisir une description. Vous pouvez utiliser la barre d’outils pour mettre en forme le texte (à l’aide du sélecteur de style, du gras, de l’italique, du souligné, de la droite, de la gauche, du centré, de la couleur, de la liste à puces) et ajouter des liens vers des informations externes. <br/>Pour terminer la modification de la description, cliquez en dehors de l’éditeur. |
| D | **Zone de fonction** | Définit la logique de la fonction. L’interface dépend du type de fonction. Voir [Référence de fonction](#function-reference) sur des informations détaillées sur chacune des fonctions prises en charge. |

{style="table-layout:auto"}

## Création d’un champ dérivé

1. Sélectionnez une vue de données existante ou créez une vue de données. Voir [Vues des données](../data-views.md) pour plus d’informations.

2. Sélectionnez la **[!UICONTROL ** Composants **]** de la vue Données.

3. Sélectionner **[!UICONTROL ** Créer un champ dérivé&#x200B;**]** dans le rail de gauche.

4. Pour définir votre champ dérivé, utilisez la méthode [!UICONTROL Créer un champ dérivé] . Voir [Interface de champ dérivée](#derived-field-interface).

   Pour enregistrer votre nouveau champ dérivé, sélectionnez **[!UICONTROL ** Enregistrer **]**.

5. Votre nouveau champ dérivé est ajouté à la variable [!UICONTROL Champs dérivés >] conteneur, dans le cadre d’ **[!UICONTROL ** Champs de schéma **]** dans le rail gauche de votre vue de données.


## Modification d’un champ dérivé

1. Sélectionnez une vue de données existante. Voir [Vues des données](../data-views.md) pour plus d’informations.

2. Sélectionnez la **[!UICONTROL ** Composants **]** de la vue Données.

3. Sélectionner **[!UICONTROL ** Champs de schéma **]** dans le [!UICONTROL Connexion] sur la gauche.

4. Sélectionner **[!UICONTROL ** Champs dérivés >**]** conteneur.

5. Pointez sur le champ dérivé à modifier, puis sélectionnez ![Icône Modifier](assets/Smock_Edit_18_N.svg).

6. Pour modifier votre champ dérivé, utilisez la méthode [!UICONTROL Modifier le champ dérivé] . Voir [Interface de champ dérivée](#derived-field-interface).

   - Sélectionner **[!UICONTROL ** Enregistrer **]** pour enregistrer votre champ dérivé mis à jour.

   - Sélectionner **[!UICONTROL ** Annuler **]** pour annuler les modifications que vous avez apportées au champ dérivé.

   - Sélectionner **[!UICONTROL ** Enregistrer sous **]** pour enregistrer le champ dérivé en tant que nouveau champ dérivé. Le nouveau champ dérivé porte le même nom que le champ dérivé modifié d’origine avec `(copy)` ajoutée à .

## Suppression d’un champ dérivé

1. Sélectionnez une vue de données existante. Voir [Vues des données](../data-views.md) pour plus d’informations.

2. Sélectionnez la **[!UICONTROL ** Composants **]** de la vue Données.

3. Sélectionner **[!UICONTROL ** Champs de schéma **]** dans [!UICONTROL Connexion] volet.

4. Sélectionner **[!UICONTROL ** Champs dérivés >**]** conteneur.

5. Pointez sur le champ dérivé à supprimer, puis sélectionnez ![Icône Modifier](assets/Smock_Edit_18_N.svg).

6. Dans l’utilisation **[!UICONTROL ** Modifier le champ dérivé&#x200B;**]** , sélectionnez Supprimer.

   A [!UICONTROL Supprimer le composant] vous demande de confirmer la suppression. Tenez compte des références externes qui peuvent exister au champ dérivé en dehors de la vue de données.

   - Sélectionner **[!UICONTROL ** Continuer **]** pour supprimer le champ dérivé.


## Modèles de fonction

Pour créer rapidement un champ dérivé en fonction de cas d’utilisation spécifiques, des modèles de fonction sont disponibles. Ces modèles de fonction sont accessibles à partir de la zone de sélecteur de l’interface de champ dérivé ou sont présentés lors de la première utilisation dans la section [!UICONTROL Commencer avec un modèle de champ] assistant.


### Canaux marketing

Ce modèle est configuré pour utiliser la variable [Analyse de l’URL](#dnl-url-parse) et [Cas lorsque](#dnl-case-when) fonctionne plusieurs fois pour obtenir les valeurs appropriées à partir d’une URL. La logique est ensuite appliquée à ces valeurs pour associer l’URL à un canal marketing spécifique.

+++ Détails

Pour utiliser le modèle, vous devez spécifier les paramètres corrects pour chaque fonction répertoriée comme faisant partie des règles du modèle. Voir [Référence de fonction](#function-reference) pour plus d’informations.

![Créateur de règles de modèle de canal marketing](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## Référence de fonction

Pour chaque fonction prise en charge, recherchez les détails ci-dessous sur :

- spécifications :
   - type de données d’entrée : type de données prises en charge,
   - input : les valeurs possibles de saisie,
   - opérateurs inclus : opérateurs pris en charge pour cette fonction (le cas échéant),
   - limit: nombre maximum de règles (avec cette fonction) que vous pouvez utiliser dans un champ dérivé,
   - sortie.

- cas d’utilisation, notamment :
   - données avant de définir le champ dérivé,
   - comment définir le champ dérivé,
   - données après avoir défini le champ dérivé.

- contraintes (le cas échéant).


<!-- Concatenate -->

### [!DNL Concatenate]

Combine plusieurs champs, champs dérivés ou valeurs saisies par l’utilisateur dans un seul champ à l’aide de délimiteurs définis.

+++ Détails

## Spécifications {#concatenate-io}

| Input Data Type | Entrée | Opérateurs inclus | Limite | Sortie |
|---|---|---|:--:|---|
| <p>Chaîne</p> | <ul><li>Deux valeurs ou plus à combiner<ul><li>Champs</li><li>Valeur dérivée d’une règle précédente</li><li>Valeur saisie par l’utilisateur</li></ul></li><li>Délimiteurs<ul><li>Saisie ou sélection d’un délimiteur pour chaque valeur</li></ul></li> </ul> | <p>S.O.</p> | <p>2</p> | <p>Nouveau champ dérivé</p> |

{style="table-layout:auto"}


## Cas d’utilisation {#concatenate-uc}

Vous collectez actuellement les codes d’origine et d’aéroport de destination comme des champs distincts. Vous souhaitez regrouper les deux champs dans une seule dimension séparée par un trait d’union (-). Vous pouvez donc analyser la combinaison de l’origine et de la destination pour identifier les itinéraires les plus réservés.

Hypothèses :

- Les valeurs d’origine et de destination sont collectées dans des champs distincts dans le même tableau.
- L’utilisateur détermine d’utiliser le délimiteur &quot;-&quot; entre les valeurs.

Imaginez que les réservations suivantes se produisent :

- ABC123 livre un vol entre Salt Lake City (SLC) et Orlando (MCO)
- Le client ABC456 livre un vol entre Salt Lake City (SLC) et Los Angeles (LAX)
- Le client ABC789 livre un vol entre Salt Lake City (SLC) et Seattle (SEA)
- ABC987 livre un vol entre Salt Lake City (SLC) et San Jose (SJO)
- ABC654 livre un vol entre Salt Lake City (SLC) et Orlando (MCO)

Le rapport souhaité doit se présenter comme suit :

| Origine/destination | Réservations |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Données avant {#concatenate-uc-databefore}

| Origine | Destination |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Champ dérivé {#concatenate-derivedfield}

Vous définissez une nouvelle [!UICONTROL Origine - Destination] champ dérivé. Vous utilisez le [!UICONTROL CONCATENATE] pour définir une règle afin de concaténer la variable [!UICONTROL Original] et [!UICONTROL Destination] à l’aide des champs `-` [!UICONTROL Délimiteur].

![[!DNL Concatenate] règle](assets/concatenate.png)

### Données après {#concatenate-dataafter}

| Origine - Destination<br/>(champ dérivé) |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- CASE WHEN -->

### [!DNL Case When]

Applique des conditions, selon des critères définis à partir d’un ou de plusieurs champs. Ces critères sont ensuite utilisés pour définir les valeurs d’un nouveau champ dérivé, selon l’ordre des conditions.

+++ Détails

## Spécifications {#casewhen-io}

| Input Data Type | Entrée | Opérateurs inclus | Limite | Sortie |
|---|---|---|:---:|---|
| <ul><li>Chaîne</li><li>Numérique</li><li>Date/Date/Heure</li></ul> | <ul><li>Champs d’entrée</li><li>Critères</li></ul> | <p><u>Chaînes</u></p><ul><li>Est égal à</li><li>Est égal à l’un des termes</li><li>Contient l’expression</li><li>Contient n’importe quel terme</li><li>Contient tous les termes</li><li>Commence par</li><li>Commence par n’importe quel terme</li><li>Se termine par</li><li>Se termine par n’importe quel terme</li><li>N’est pas égal à</li><li>N’est égal à aucun terme</li><li>Ne contient pas l’expression</li><li>Ne contient aucun terme</li><li>Ne contient pas tous les termes</li><li>Ne commence pas par</li><li>Ne commence par aucun terme</li><li>Ne se termine pas par</li><li>Ne se termine par aucun terme</li><li>Est défini</li><li>N’est pas défini</li></ul><p><u>Numérique</u></p><ul><li>Est égal à</li><li>N’est pas égal à</li><li>Est supérieur à</li><li>Est supérieur ou égal à</li><li>Est inférieur à</li><li>Est inférieur ou égal à</li><li>Est défini</li><li>N’est pas défini</li></ul><p><u>Dates</u></p><ul><li>Est égal à</li><li>N’est pas égal à</li><li>Est postérieur à</li><li>Est ultérieur ou égal à</li><li>Est avant</li><li>Est antérieur ou égal à</li><li>Est défini</li><li>N’est pas défini</li></ul> | <p>5</p> | <p>Nouveau champ dérivé</p> |

{style="table-layout:auto"}


## Cas d’utilisation 1 {#casewhen-uc1}

Vous souhaitez définir des règles pour identifier différents canaux marketing, en appliquant une logique en cascade pour définir un champ de canal marketing sur la valeur appropriée :

- Si le référent provient d’un moteur de recherche et que la page comporte une valeur de chaîne de requête où `cid` contains `ps_`, le canal marketing doit être identifié comme [!DNL *Recherche payante*].
- Si le référent provient d’un moteur de recherche et que la page ne comporte pas de chaîne de requête `cid`, le canal marketing doit être identifié comme [!DNL *Recherche naturelle*].
- Si une page a une valeur de chaîne de requête où `cid` contains `em_`, le canal marketing doit être identifié en tant que [!DNL *Email*].
- Si une page a une valeur de chaîne de requête où `cid` contains `ds_`, le canal marketing doit être identifié comme [!DNL *Afficher la publicité*].
- Si une page a une valeur de chaîne de requête où `cid` contains `so_`, le canal marketing doit être identifié comme [!DNL *Social payant*].
- Si le référent provient d’un domaine référent de [!DNL twitter.com], [!DNL facebook.com], [!DNL linkedin.com]ou [!DNL tiktok.com], le canal marketing doit être identifié comme [!DNL *Social naturel*].
- Si aucune des règles ci-dessus ne correspond, le canal marketing doit être identifié comme [!DNL *Autre référent*].

Si votre site reçoit les exemples d’événements suivants, contenant [!UICONTROL Référent] et [!UICONTROL URL de la page], ces événements doivent être identifiés comme suit :

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 |  | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### Données avant {#casewhen-uc1-databefore}

| [!UICONTROL Référent] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### Champ dérivé {#casewhen-uc1-derivedfield}

Vous définissez une nouvelle `Marketing Channel` champ dérivé. Vous utilisez le [!UICONTROL CAS LORSQUE] fonctions permettant de définir des règles qui créent des valeurs pour en fonction des valeurs existantes pour les deux fonctions `Page URL` et `Referring URL` champ .

Notez l’utilisation de la fonction [!UICONTROL URL PARSE] pour définir des règles pour récupérer les valeurs de `Page Url` et `Referring Url` avant l’événement [!UICONTROL CAS LORSQUE] sont appliquées.

![[!DNL Case when] règle 1](assets/case-when-1.png)

### Données après {#casewhen-uc1-dataafter}

| [!DNL Marketing Channel] |
|----|
| [!DNL Natural Social] |
| [!DNL Display] |
| [!DNL Email] |
| [!DNL Paid Search] |
| [!DNL Email] |
| [!DNL Natural Search] |

{style="table-layout:auto"}


## Cas d’utilisation 2 {#casewhen-uc2}

Vous avez collecté plusieurs variantes de recherche dans votre [!DNL Product Finding Methods] dimension. Pour comprendre les performances globales de la recherche par rapport à la navigation, vous devez passer beaucoup de temps à combiner les résultats manuellement.

Votre site collecte les valeurs suivantes pour votre [!DNL Product Finding Methods] dimension. À la fin, toutes ces valeurs indiquent une recherche.

| Valeur collectée | Valeur réelle |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes ] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### Données avant {#casewhen-uc2-databefore}

| [!DNL Product Finding Methods] |
|----|
| [!DNL search p13_no] |
| [!DNL search p13_yes] |
| [!DNL browse] |
| [!DNL search refine p13_no] |
| [!DNL search refine p13_yes] |
| [!DNL browse] |
| [!DNL search redirect p13_yes] |
| [!DNL search-redirect] |
| [!DNL browse] |

{style="table-layout:auto"}

### Champ dérivé {#casewhen-uc2-derivedfield}

Vous définissez une `Product Finding Methods (new)` champ dérivé. Vous créez les éléments suivants : [!UICONTROL CAS LORSQUE] règles dans le créateur de règles. Ces règles appliquent la logique à toutes les variantes possibles de l’ancienne [!UICONTROL Méthodes de recherche de produits] valeurs de champ pour `search` et `browse` en utilisant la variable [!UICONTROL Contient l’expression] critère.

![[!DNL Case When] règle 2](assets/case-when-2.png)

### Données après {#casewhen-uc2-dataafter}

| [!DNL Product Finding Methods (new)] |
|----|
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |

{style="table-layout:auto"}


## Cas d’utilisation 3 {#casewhen-uc3}

En tant qu’agence de voyages, vous souhaitez regrouper la durée des voyages réservés afin que vous puissiez établir des rapports sur la durée des voyages regroupés.

Hypothèses :

- L’organisation collecte la durée du voyage dans un champ numérique.
- Ils souhaitent regrouper des durées de 1 à 3 jours dans un compartiment appelé &quot;&quot;[!DNL short trip]&#39;
- Ils souhaitent regrouper des durées de 4 à 7 jours dans un compartiment appelé &quot;&quot;[!DNL medium trip]&#39;
- Ils souhaitent regrouper 8 durées de plus de 8 jours dans un compartiment appelé &quot;&quot;[!DNL long trip]&#39;
- 132 trajets ont été réservés pour une durée d&#39;une journée
- 110 trajets ont été réservés pour une durée de 2 jours
- 105 trajets ont été réservés pour une durée de 3 jours
- 99 trajets ont été réservés pour une durée de 4 jours
- 92 trajets ont été réservés pour une durée de 5 jours
- 85 trajets ont été réservés pour une durée de 6 jours
- 82 trajets ont été réservés pour une durée de 7 jours
- 78 trajets ont été réservés pour une durée de 8 jours
- 50 trajets ont été réservés pour une durée de 9 jours
- 44 trajets ont été réservés pour une durée de 10 jours
- 38 trajets ont été réservés pour une durée de 11 jours
- 31 trajets ont été réservés pour une durée de 12 jours

Le rapport souhaité doit se présenter comme suit :

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### Données avant {#casewhen-uc3-databefore}

| [!DNL Trip Duration] |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

### Champ dérivé {#casewhen-uc3-derivedfield}

Vous définissez une `Trip Duration (bucketed)` champ dérivé. Vous créez les éléments suivants : [!UICONTROL CAS LORSQUE] dans le créateur de règles. Cette règle applique la logique pour regrouper l’ancienne [!UICONTROL Durée du voyage] valeurs de champ en trois valeurs : `short trip`, `medium  trip`, et `long trip`.

![[!DNL Case When] règle 3](assets/case-when-3.png)


### Données après {#casewhen-uc3-dataafter}

| [!DNL Trip Duration (bucketed)] |
|---|
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL short trip] |
| [!DNL medium trip] |
| [!DNL medium trip] |
| [!DNL long trip] |
| [!DNL medium trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL long trip] |


## Contraintes

CJA utilise une structure de conteneur imbriquée, modelée sur le Adobe Experience Platform. [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) (Modèle de données d’expérience). Voir [Conteneurs](../create-dataview.md#containers) et [Filtrage des conteneurs](../../components/filters/filters-overview.md#filter-containers) pour plus d’informations. Ce modèle de conteneur, bien que flexible par nature, impose certaines contraintes lors de l’utilisation du créateur de règles.

CJA utilise le modèle de conteneur par défaut suivant :

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>



Les contraintes suivantes s’appliquent et sont appliquées lorsque *Sélection* et *paramètre* valeurs.

|  | Contraintes |
|:---:|----|
| **<span style='color: red'>A</span>** | Valeurs *select* dans le même [!UICONTROL If], [!UICONTROL Sinon si] concept (à l’aide de [!UICONTROL Et] ou [!UICONTROL Ou]) d’une règle doit provenir du même conteneur et peut être de n’importe quel type (chaîne ![Chaîne](assets/Smock_ABC_18_N.svg), numérique ![Numérique](assets/Smock_123_18_N.svg), etc.). <br/>![Dépendance A](assets/dependency-a.png) |
| **<span style='color: red'>B</span>** | Toutes les valeurs que vous *set* dans une règle doit provenir du même conteneur et avoir le même type ou une valeur dérivée du même type. <br/> ![Dépendance B](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | Les valeurs que vous *select* cross [!UICONTROL If], [!UICONTROL Sinon si] éléments dans la règle do *not* doivent provenir du même conteneur et doivent *not* doivent être du même type. <br/> ![Dépendance C](assets/dependency-c.png) |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### [!DNL Find and Replace]

Recherche toutes les valeurs d’un champ sélectionné et remplace ces valeurs par une valeur différente dans un nouveau champ dérivé.

+++ Détails

## Spécifications {#findreplace-io}

| Input Data Type | Entrée | Opérateurs inclus | Limite | Sortie |
|---|---|---|:---:|---|
| <p>Chaîne</p> | <ul><li><span>Critères de champ &quot;Quand remplacer&quot;</span></li><li><span>Valeur de champ &quot;Remplacer par&quot;</span><ul><li><span>Entré par l’utilisateur</span></li><li><span>Champ distinct</span></li></ul></li></ul> | <p><u>Chaînes</u></p><ul><li>Tout rechercher et tout remplacer</li></ul> | <p>1</p> | <p>Nouveau champ dérivé</p> |

{style="table-layout:auto"}


## Cas d’utilisation {#findreplace-uc}

Vous avez reçu des valeurs incorrectes pour votre rapport de canaux marketing externes, par exemple `email%20 marketing` au lieu de `email marketing`. Ces valeurs incorrectes divisent vos rapports et rendent plus difficile l’affichage des performances des emails. Vous souhaitez remplacer `email%20marketing` avec `email marketing`.

**Rapport d’origine**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**Rapport Préféré**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### Données avant {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### Champ dérivé {#findreplace-uc-derivedfield}

Vous pouvez définir une `Email Marketing (updated)` champ dérivé. Vous utilisez le [!UICONTROL RECHERCHER ET REMPLACER] pour définir une règle permettant de rechercher et remplacer toutes les occurrences de `email%20marketing` avec `email marketing`.

![[!DNL Find and Replace] règle](assets/find-and-replace.png)

### Données après {#findreplace-uc-dataafter}

| [!DNL External Marketing (updated)] |
|----|
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### [!DNL Lookup]

Définit un ensemble de valeurs de recherche qui sont remplacées par les valeurs correspondantes.

+++ Détails


## Spécifications {#lookup-io}

| Input Data Type | Entrée | Opérateurs inclus | Limite | Sortie |
|---|---|---|:---:|---|
| <ul><li>Chaîne</li><li>Numérique</li><li>Date</li></ul> | <ul><li>Champ unique</li><li>Fichier de recherche<ul><li>Colonne de clé</li><li>Nouvelle colonne de champ</li></ul></li></ul> | <p>S.O.</p> | <p>5</p> | <p>Nouveau champ dérivé</p> |

{style="table-layout:auto"}


## Cas d’utilisation 1 {#lookup-uc1}

Vous disposez d’un fichier CSV contenant une colonne clé pour `hotelID` et une ou plusieurs colonnes supplémentaires associées à la variable `hotelID`: `city`, `rooms`, `hotel name`.
Vous collectez des [!DNL Hotel ID] dans une dimension, mais que souhaitez-vous créer [!DNL Hotel Name] dimension dérivée de `hotelID` dans le fichier CSV.

**Structure et contenu du fichier CSV**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |

{style="table-layout:auto"}

**Rapport actuel**

| [!DNL Hotel ID] | Consultations de produit |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |

{style="table-layout:auto"}


**Rapport souhaité**

| [!DNL Hotel Name] | Consultations de produit |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### Données avant {#lookup-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |

{style="table-layout:auto"}


### Champ dérivé {#lookup-uc1-derivedfield}

Vous définissez une `Hotel Name` champ dérivé. Vous utilisez le [!UICONTROL RECHERCHE] pour définir une règle dans laquelle vous pouvez rechercher les valeurs de la fonction [!UICONTROL ID de l&#39;hôtel] et remplacez par de nouvelles valeurs.

![[!DNL Lookup] règle 1](assets/lookup-1.png)

### Données après {#lookup-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## Cas d’utilisation 2 {#lookup-uc2}

Vous avez collecté des URL au lieu du nom de page convivial pour plusieurs pages. Cette collection mixte de valeurs rompt la création de rapports.

### Données avant {#lookup-uc2-databefore}

| [!DNL Page Name] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| [!DNL Deals & Offers] |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### Champ dérivé {#lookup-uc2-derivedfield}

Vous définissez une `Page Name (updated)` champ dérivé. Vous utilisez le [!UICONTROL RECHERCHE] pour définir une règle dans laquelle vous pouvez rechercher les valeurs de votre [!UICONTROL Nom de la page] et remplacez par les valeurs correctes mises à jour.

![[!DNL Lookup] règle 2](assets/lookup-2.png)

### Données après {#lookup-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |

+++

<!-- URL PARSE -->

### [!DNL URL Parse]

Analyse différentes parties d’une URL, y compris le protocole, l’hôte, le chemin ou les paramètres de requête.

+++ Détails

## Spécifications {#urlparse-io}

| Input Data Type | Entrée | Opérateurs inclus | Limite | Sortie |
|---|---|---|:---:|---|
| <ul><li>Chaîne</li></ul> | <ul><li>Champ unique</li><li>Option d’analyse<ul><li>Obtenir le protocole</li><li>Obtenir lʼhôte</li><li>Obtenir le chemin d’accès</li><li>Obtenir la valeur de la requête<ul><li>Paramètre de requête</li></ul></li><li>Obtenir la valeur de hachage</li></ul></li></ul></li></ul> | <p>S.O.</p> | <p>5</p> | <p>Nouveau champ dérivé</p> |

{style="table-layout:auto"}


## Cas d’utilisation 1 {#urlparse-uc1}

Vous souhaitez uniquement utiliser le domaine référent de l’URL de référence dans le cadre de l’ensemble de règles d’un canal marketing.

### Données avant {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### Champ dérivé {#urlparse-uc1-derivedfield}

Vous définissez une  `Referring Domain` champ dérivé. Vous utilisez le [!UICONTROL URL PARSE] pour définir une règle permettant de récupérer l’hôte à partir de la fonction [!UICONTROL URL de référence] et stockez-les dans le nouveau champ dérivé.

![[!DNL Url Parse] règle 1](assets/url-parse-1.png)

### Données après {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## Cas d’utilisation 2 {#urlparse-uc2}

Vous souhaitez utiliser la valeur de la variable `cid` paramètre d’une chaîne de requête dans une [!DNL Page URL] dans le cadre de la sortie d’un rapport de code de suivi dérivé.

### Données avant {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### Champ dérivé {#urlparse-uc2-derivedfield}

Vous définissez une `Query String CID` champ dérivé. Vous utilisez le [!UICONTROL URL PARSE] pour définir une règle permettant de récupérer la valeur du paramètre de chaîne de requête dans la variable [!UICONTROL URL de la page] champ, spécification `cid` comme paramètre de requête. La valeur de sortie est stockée dans le nouveau champ dérivé.

![[!DNL Url Parse] règle 2](assets/url-parse-2.png)

### Données après {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++
