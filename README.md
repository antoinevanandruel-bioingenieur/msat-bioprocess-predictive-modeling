## 🤖 [Projet 2 : MSAT Bioprocess Predictive Modeling](https://github.com)

Ce module déploie un algorithme de Machine Learning (Régression Linéaire Multiple avec Scikit-Learn) pour modéliser et anticiper les cinétiques de croissance cellulaire.
* **Inputs capteurs :** pH et Oxygène Dissous (DO_Percent)
* **Output prédictif :** Densité Cellulaire Viable (VCD)
* **Objectif industriel :** Anticiper les dérives de batch avant la fin du cycle de culture.

## 📊 Méthodologie & Validation Métrologique

Pour garantir la fiabilité de ces prédictions de Densité Cellulaire Viable (VCD) dans un cadre GxP, le modèle est audité via deux métriques standard :

### 1. Mean Squared Error (MSE)
La MSE mesure la moyenne des carrés des écarts entre les prédictions du modèle et les valeurs réelles de production.
* **Formule mathématique :** 
  $$MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$
* **Pourquoi le carré ?** Élever l'erreur au carré permet d'éliminer les signes négatifs et de pénaliser de manière exponentielle les écarts importants (Outliers).

### 2. Root Mean Squared Error (RMSE)
Dans le script, nous appliquons la racine carrée à la MSE ($\sqrt{MSE}$). Cela permet de ramener l'indicateur d'erreur à l'unité de mesure biologique réelle (en Millions de cellules par mL), rendant l'interprétation exploitable.
