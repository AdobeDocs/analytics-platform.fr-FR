---
title: Avertissements
description: Avertissements pour l’extension BI dans divers outils BI de Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Avertissements


Chacun des outils de BI pris en charge comporte certains avertissements concernant l’utilisation de l’extension Customer Journey Analytics BI.

+++ Outils de BI

>[!BEGINTABS]

>[!TAB Bureau Power BI]

* Le filtrage des périodes avancé de Power BI Desktop est exclusif.  Pour votre date de fin, vous devez sélectionner une date postérieure à la journée pour laquelle vous souhaitez créer un rapport. Par exemple, **[!UICONTROL est le ou après]** `1/1/2023` **[!UICONTROL et avant]** `1/2/2023`.
* Power BI Desktop est défini par défaut sur **[!UICONTROL Importer]** lorsque vous créez une connexion. Veillez à utiliser **[!UICONTROL Requête directe]**.
* Power BI Desktop expose les transformations de données via Power Query.  Power Query fonctionne principalement avec des connexions de type Import de sorte que de nombreuses transformations que vous appliquez comme des fonctions de date ou de chaîne génèrent une erreur indiquant que vous devez passer à une connexion de type Import.  Si vous devez transformer les données au moment de la requête, vous devez utiliser des dimensions et des mesures dérivées afin que Power BI n’ait pas besoin d’effectuer les transformations lui-même.
* Power BI Desktop ne comprend pas comment gérer les colonnes de type date et heure. Les dimensions **[!UICONTROL daterange *X *]**telles que**[!UICONTROL daterangehour ]**et**[!UICONTROL daterangeminute ]**ne sont donc pas prises en charge.
* Par défaut, Power BI Desktop tente d’établir plusieurs connexions à l’aide d’un plus grand nombre de sessions Query Service.  Accédez aux paramètres Power BI de votre projet et désactivez les requêtes parallèles.
* Power BI Desktop effectue tout le tri et la limitation côté client. Power BI Desktop propose également une sémantique différente pour le filtrage top *X* qui inclut les valeurs liées. Vous ne pouvez donc pas créer le même tri et la même limitation que dans Analysis Workspace.
* Les versions antérieures de Power BI Desktop d’octobre 2024 interrompent les sources de données PostgreSQL. Veillez à utiliser la version mentionnée dans cet article.

>[!TAB  Tableau Desktop ]

* Le filtrage de la plage de dates de Tableau Desktop est exclusif. Pour votre date de fin, vous devez sélectionner une date postérieure à la journée pour laquelle vous souhaitez créer un rapport.
* Par défaut, lorsque vous ajoutez une dimension date ou date-heure telle que **[!UICONTROL Daterangemonth]** aux lignes d&#39;une feuille, Tableau Desktop enveloppe le champ dans une fonction **[!UICONTROL YEAR()]**.  Pour obtenir ce que vous souhaitez, vous devez sélectionner cette dimension et, dans le menu déroulant, sélectionner la fonction de date à utiliser.  Par exemple, redéfinissez **[!UICONTROL Année]** sur **[!UICONTROL Mois]** lorsque vous essayez d’utiliser **[!UICONTROL Mois du suivi]**.
* Limiter les résultats au *X* supérieur n&#39;est pas évident dans Tableau Desktop. Vous pouvez limiter les résultats de manière explicite ou à l’aide d’un champ calculé et de la fonction **[!UICONTROL INDEX()]**.  L’ajout d’un filtre Top *X* à une dimension génère un SQL complexe à l’aide d’une jointure interne qui n’est pas prise en charge.

>[!TAB Looker]

* Le sélecteur de possède un nombre maximal de connexions par paramètre de nœud qui doit être compris entre 5 et 100.  Vous ne pouvez pas définir cette valeur sur 1.  Ce paramètre implique qu’une connexion de recherche utilise toujours au moins 5 des sessions Query Service disponibles.
* L’outil de recherche vous permet de créer un projet avec une vue basée sur une vue de données Customer Journey Analytics. Looker crée ensuite un modèle basé sur les dimensions et les mesures, disponibles dans la vue Données, à l’aide de LookerML.  Cette vue de projet n&#39;est pas automatiquement mise à jour pour correspondre à la source.  Si vous apportez des modifications ou des ajouts aux dimensions, mesures, mesures calculées ou segments de la Vue de données CJA, ces modifications ne s’affichent pas automatiquement dans l’outil de recherche.  Vous devez mettre à jour manuellement la vue du projet ou créer un nouveau projet.
* L’expérience utilisateur de la recherche sur les champs de date ou d’heure tels que **[!UICONTROL Date de plage]** ou **[!UICONTROL Date de plage]** est déroutante.
* La période de l’observateur n’est pas inclusive, mais exclusive.  Le **[!UICONTROL jusqu’au (avant)]** est en gris, vous pouvez donc passer à côté de cet aspect.  Pour votre jour de fin, vous devez sélectionner une heure et demie le jour pour lequel vous souhaitez créer un rapport.
* Looker ne traite pas automatiquement vos mesures comme des mesures .  Lorsque vous sélectionnez une mesure, par défaut, Looker tente de la traiter comme une dimension dans la requête.  Pour traiter une mesure comme une mesure, vous devez créer un champ personnalisé, comme illustré ci-dessus. Comme raccourci, vous pouvez sélectionner **[!UICONTROL ⋮]**, **[!UICONTROL Agréger]**, puis sélectionner **[!UICONTROL Somme]**.

>[!TAB Notebook Jupyter]

* L’avertissement principal pour Jupyter Notebook est que l’outil n’est pas une interface utilisateur par glisser-déposer comme les autres outils de BI. Vous pouvez créer de bons visuels, mais vous devez écrire du code pour y parvenir.

>[!TAB RStudio]

* R dplyr fonctionne avec un schéma aplati. L’option **[!UICONTROL FLATTEN]** est donc requise.
* L’avertissement principal pour RStudio est que l’outil n’est pas une interface utilisateur par glisser-déposer comme les autres outils de BI. Vous pouvez créer de bons visuels, mais vous devez écrire du code pour y parvenir.

>[!ENDTABS]

+++
