---
title: Libellés Restreints Dans Report Builder
description: Découvrez les libellés restreints dans Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
TQID: https://experienceleague.adobe.com/MeHO7A9KWAjG8TyiOn9taPbtPhD47JGl88KSCoQwdMI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: f2ef16dc-055a-4bb7-baa5-7039653f3966id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 39%

---

# Libellés restreints dans Report Builder

En règle générale, les paramètres liés à la gouvernance de données dans Customer Journey Analytics sont hérités d’Experience Platform. L’intégration entre la gouvernance des données Customer Journey Analytics et Experience Platform permet l’étiquetage des données Customer Journey Analytics sensibles et l’application des politiques de confidentialité.

Les étiquettes de confidentialité et les politiques créées sur les jeux de données consommés par Experience Platform peuvent être affichées dans le workflow des vues de données Customer Journey Analytics. Ces libellés arrêtent ou avertissent les utilisateurs qui créent des mesures et des dimensions à partir de champs sensibles. Pour plus d’informations sur les jeux de données, consultez la [Présentation des jeux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/catalog/datasets/overview)

En outre, lorsque des données sont exportées à partir de Customer Journey Analytics (par le biais de rapports, d’exports, d’API, etc.), des avertissements ou des libellés sont ajoutés afin d’informer les personnes qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique.

Cette intégration vous permet de gérer la conformité. Les gestionnaires de données de votre entreprise peuvent définir des politiques pour restreindre l’utilisation. Par conséquent, vos utilisateurs et utilisatrices Customer Journey Analytics peuvent utiliser les données de manière plus sécurisée, tout en sachant qu’elles sont conformes aux politiques définies par les gestionnaires de données.

Pour plus d’informations, voir [Customer Journey Analytics et gouvernance des données](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-privacy/privacy-overview)

## Afficher les données limitées

Deux politiques définies par Adobe sont affichées dans Customer Journey Analytics et affectent la création de rapports, le téléchargement et le partage :

* Politique Application d’Analytics
* Politique Application du téléchargement

Les composants soumis à ces politiques sont grisés et possèdent une icône ![InfoOutline](/help/assets/icons/InfoOutline.svg). Lorsque vous pointez sur l’icône d’informations, une note s’affiche pour indiquer les éléments suivants : **[!UICONTROL Des politiques ont été appliquées à ce champ pour interdire l’utilisation de ces données]**.

Pour plus d’informations, voir [ Étiquettes et politiques ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance).


![Note de politique indiquant l’utilisation interdite des données.](assets/restricted-label.png){zoomable="yes"}


## Mettre à jour les rapports contenant des données restreintes

Dans les cas où un utilisateur a créé un rapport Report Builder avec des éléments de données ultérieurement limités, un message d’erreur s’affiche lorsque le rapport est actualisé.

![Message d’erreur affiché après la restriction ultérieure des éléments de données.](assets/error-restricted-data.png){width="100%" zoomable="yes"}
