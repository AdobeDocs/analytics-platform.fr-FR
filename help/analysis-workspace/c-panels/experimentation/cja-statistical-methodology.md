---
source-git-commit: 99b190e1afe7068d11fd9d53c5be72008958a9c2
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---
# Présentation de la méthodologie statistique dans le panel d’expérimentation de CJA

Cet article décrit les calculs statistiques utilisés par le panneau d’expérience dans CJA. CJA utilise des méthodes statistiques avancées pour calculer **confiance** qui est valide à tout moment, ce qui vous permet d’exécuter vos expériences aussi longtemps que vous le souhaitez et de surveiller vos résultats en continu.

Cet article décrit le fonctionnement des tests A/B et présente de manière intuitive le fonctionnement des Adobes. ***Tout moment de séquence de confiance valide***. Pour les utilisateurs experts, les détails techniques et les références sont inclus à la fin.

## Test A/B et cause à effet

Les tests A/B sont souvent décrits comme un &quot;étalon-or&quot; dans l’évaluation de l’impact causal d’un type d’&quot;intervention&quot;. Il s’agit d’essais randomisés, ce qui, dans le cadre de tests en ligne, signifie que nous exposons certains utilisateurs sélectionnés de manière aléatoire à une variation donnée d’un site web, d’un message ou d’un email, et un autre ensemble d’utilisateurs sélectionnés de manière aléatoire à d’autres. **variant** ou **traitement**. Après exposition, nous mesurons ensuite le résultat **mesure(s)** nous nous intéressons à (par exemple, ouvertures d’emails, abonnements ou achats).

Comme illustré dans l’image ci-dessous, le fait que nous ayons assigné de manière aléatoire des utilisateurs à chaque groupe de variantes signifie qu’en moyenne, les groupes partagent les mêmes caractéristiques. Ainsi, toute différence de résultats peut être interprétée comme étant due aux différences dans les variantes reçues, c&#39;est-à-dire que nous sommes en mesure d&#39;établir une **causal** lien entre nos interventions et les résultats qui nous intéressent. Cela vous permet de prendre des décisions rigoureuses, explicables et basées sur les données pour optimiser vos objectifs commerciaux. Les tests A/B sont donc une partie essentielle de la boîte à outils de tout praticien de la personnalisation moderne.

<p style="text-align:center;"><img width="75%" src="img/causal-inference-cartoon.png" alt="causal-inf"></p>


Maintenant, une question importante est de savoir si les différences observées sont des &quot;effets réels&quot;, ou surviennent à cause du hasard. Intuitivement, s’il n’y a qu’une petite différence dans les mesures des résultats entre les groupes, cela aurait pu être observé par hasard, alors que les différences plus importantes sont plus susceptibles d’être &quot;réelles&quot;. Le terme technique ici est que nos mesures sont *estimations* des valeurs réelles de la moyenne pour chaque groupe de variantes. Les techniques d&#39;inférence statistique nous permettent de quantifier la quantité d&#39;incertitude dans nos estimations. C&#39;est là que les concepts de **p-values** et **Intervalles de confiance** mais pour les comprendre, nous devons d’abord comprendre les erreurs statistiques.

## Erreurs de test et de contrôle statistiques

De nombreuses méthodologies d&#39;inférence statistique sont conçues pour contrôler deux types d&#39;erreurs : **Faux positifs** (erreurs de type I) et **Faux négatifs** (Erreurs de type II). Elles sont illustrées dans le tableau ci-dessous.


<p style="text-align:center;"><img width="50%" src="img/contingency_table_stats_errors.png" alt="ContingenceTable"></p>


Un faux positif est un rejet incorrect de l’hypothèse nulle, alors qu’en fait elle est vraie. Dans le contexte des tests A/B en ligne, cela signifie que nous concluons (à tort) que la mesure commerciale des résultats est différente entre les différentes armes, alors qu&#39;en fait elle était la même. Avant de lancer l&#39;expérience, nous sélectionnons généralement un seuil *α*. Une fois l’expérience terminée, la variable *p*-value est calculé, et nous rejetons la valeur null si *p &lt; alpha*. Un seuil couramment utilisé est : *α*= 0,05, ce qui signifie qu&#39;à long terme, nous nous attendons à ce que 5 expériences sur 100 soient des faux positifs.

Pendant ce temps, un faux négatif signifie que nous ne parvenons pas à rejeter l&#39;hypothèse nulle alors qu&#39;en fait elle est fausse. Pour les tests A/B, cela signifie que nous ne rejetons pas l’hypothèse nulle (rappelez-vous, l’hypothèse nulle indique que la mesure commerciale des résultats est la même entre les bras de variante), alors qu’en fait elle est différente. Pour contrôler ce type d’erreur, nous avons généralement besoin d’un nombre suffisant d’utilisateurs dans notre expérience pour garantir qu’un **Puissance**, défini sur 1-*ß* (soit moins la probabilité d’une erreur de type II).

La plupart des techniques d’inférencement statistique nécessitent que vous fixiez à l’avance la taille de l’échantillon, en fonction de la taille de l’effet que vous souhaitez déterminer, ainsi que votre tolérance d’erreur (*α* et *ß*) en avance. Toutefois, la méthodologie d’Adobe est conçue pour vous permettre d’examiner en permanence vos résultats, quelle que soit la taille de l’échantillon.



## Méthodologie statistique de l’Adobe : _À Tout Moment De Séquences De Confiance Valides_

Afin de fournir une inférence statistique facile à interpréter et sûre, l&#39;Adobe a adopté une méthodologie statistique fondée sur des [_À Tout Moment De Séquences De Confiance Valides_](https://doi.org/10.48550/arXiv.2103.06476).

Une séquence de confiance est une analogie &quot;séquentielle&quot; d’un intervalle de confiance. Pour comprendre ce qu’est une séquence de confiance, imaginez répéter vos expériences cent fois et calculer une estimation de la mesure commerciale moyenne (par exemple, le taux d’ouverture d’un email) et de la séquence de confiance à 95 % qui lui est associée pour *chaque nouvel utilisateur* qui entre dans l&#39;expérience. Une séquence de confiance de 95 % inclura la valeur &quot;true&quot; de la mesure commerciale dans 95 des 100 expériences que vous avez exécutées. (Un intervalle de confiance de 95 % ne pouvait être calculé qu&#39;une seule fois par expérience afin de garantir la même couverture de 95 % ; pas avec chaque nouvel utilisateur). Les séquences de confiance vous permettent donc de surveiller en permanence les expériences, sans augmenter les taux d’erreur Faux positif, c’est-à-dire qu’elles permettent de &quot;regarder&quot; les résultats.

La différence entre les séquences de confiance et les intervalles de confiance pour une seule expérience est illustrée dans l’animation ci-dessous :

<p style="text-align:center;"><img width="75%" src="img/confidence-sequence-evolution-comparison.gif" alt="CSGIF"></p>


Nous remarquons que les séquences de confiance déplacent la cible des tests A/B vers *estimation* plutôt que de tester les hypothèses, c&#39;est-à-dire de se concentrer sur une estimation précise de la différence de moyens entre traitements, plutôt que de rejeter ou non une hypothèse nulle basée sur un seuil de signification statistique.

Cependant, de la même manière que la relation entre les valeurs $p$ (ou le degré de confiance) et les intervalles de confiance, il existe également une relation entre les séquences de confiance et toutes les valeurs $p$-valides (ou tout degré de confiance valide). Compte tenu de la familiarité de quantités comme le degré de confiance, CJA fournit le degré de confiance en tout temps valide dans ses rapports.

Les fondements théoriques des séquences de confiance viennent de l&#39;étude de séquences de variables aléatoires connues sous le nom de martingales. Voici quelques résultats principaux pour les lecteurs experts, mais les recommandations pour les praticiens sont claires :


> Les séquences de confiance peuvent être interprétées comme des analogies séquentielles &quot;sûres&quot; d’intervalles de confiance : vous pouvez consulter et interpréter les données de votre test A/B à tout moment, et arrêter ou poursuivre des expériences en toute sécurité. Confiance valide en tout temps correspondante (ou *p*-value) est également sûr à interpréter.

Il est important de noter que la méthodologie statistique étant &quot;valable à tout moment&quot;, elle sera plus prudente qu’une méthodologie à horizon fixe appliquée à la même taille d’échantillon. Cela signifie que le paramètre &quot;n’importe quand valide&quot; *p* Les valeurs sont généralement supérieures à l’horizon fixe correspondant. *p*-values (c’est-à-dire que le degré de confiance valide sera plus faible à tout moment)

## Interprétation des résultats

1. **L&#39;expérience est concluante**: Chaque fois que vous consultez le rapport d’expérimentation, Adobe analyse les données accumulées jusqu’à présent dans l’expérience et déclare une expérience comme &quot;concluante&quot; lorsque la confiance valide dépasse un seuil de 95 % pour *au moins un* des variantes (avec une correction Bonferonni appliquée lorsqu&#39;il y a plus de deux bras, afin de corriger pour plusieurs tests d&#39;hypothèse).

2. **Variante la plus performante**: Lorsqu’une expérience est déclarée concluante, la variante ayant le taux de conversion le plus élevé est étiquetée comme &quot;variante la plus performante&quot;. Notez que cette variante doit être la variante de référence ou de contrôle, ou l’une des variantes qui dépasse les 95 % chaque fois que le seuil de confiance valide (avec des corrections Bonferonni appliquées).

3. **Taux de conversion**: Le taux de conversion qui s’affiche est un ratio de la valeur de la mesure de succès par rapport à la valeur de la mesure de normalisation. Notez que cette valeur peut parfois être supérieure à 1, si la mesure n’est pas binaire (1 ou 0 pour chaque unité de l’expérience).

4. **Effet élévateur**: Le résumé du rapport d’expérience affiche l’effet élévateur sur la ligne de base, qui est une mesure de l’amélioration en pourcentage du taux de conversion d’une variante donnée par rapport à la ligne de base. Défini précisément, il s’agit de la différence de performance entre une variante donnée et la ligne de base, divisée par les performances de la ligne de base, exprimée en pourcentage.

5. **Confiance**: La fiabilité en tout temps qui s’affiche est une mesure probabiliste de l’ampleur des preuves qu’une variante donnée est identique à la variante témoin. Une confiance plus élevée indique moins de preuves que la variante de contrôle et la variante de non-contrôle ont des résultats égaux. Plus précisément, la confiance affichée est une probabilité (exprimée en pourcentage) que nous aurions observée une différence plus faible dans les taux de conversion entre une variante donnée et le contrôle, si en réalité il n’y a aucune différence dans les taux de conversion réels sous-jacents. En termes de *p*-values, la confiance affichée est 1 - *p*-value.

Notez toutefois qu’une description complète des résultats doit tenir compte de toutes les preuves disponibles (c’est-à-dire la conception de l’expérience, la taille des échantillons, les taux de conversion, le degré de confiance, etc.), et pas seulement de la déclaration concluante ou non. Même lorsqu’un résultat n’est pas encore &quot;concluant&quot;, il peut encore y avoir des preuves convaincantes pour qu’une variante soit différente d’une autre (par exemple, les intervalles de confiance sont presque sans chevauchement). Idéalement, la prise de décision doit être fondée sur toutes les données statistiques, interprétées sur un spectre continu.
