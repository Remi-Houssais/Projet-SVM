# Objectif du projet

Dans le cadre de ce projet de machine learning, l’objectif est d’analyser et de modéliser la qualité du vin à partir d’un jeu de données comportant plus de 4000 observations.

Dans un premier temps, la variable cible (qualité du vin) a été étudiée comme une variable **quantitative**, ce qui nous a conduits à estimer des modèles de **régression** afin d’analyser la relation entre les caractéristiques du vin et sa qualité.

Dans un second temps, afin de simplifier le problème et de se rapprocher d’une problématique de décision (bonne vs mauvaise qaulité de vin), la variable cible a été transformée en une variable **binaire**. Le problème devient alors un problème de **classification**.

L’enjeu principal est de comparer les performances de plusieurs modèles de machine learning, notamment :
- les modèles linéaires,
- les modèles de type forêts aléatoires,
- et les **machines à vecteurs de support (SVM)**.

Une attention particulière est portée au modèle SVM, qui constitue le cœur de l’analyse. Ce modèle est particulièrement intéressant car il permet de capturer des relations non linéaires entre les variables explicatives et la qualité du vin grâce à l’utilisation de fonctions noyaux (*kernels*).

---

# Démarche méthodologique

Le projet suit une démarche structurée en plusieurs étapes, allant de l’exploration des données à la modélisation.

## 1. Exploration et analyse des données

Dans un premier temps, un travail approfondi a été réalisé sur le dataset :

- Nettoyage des données (gestion des valeurs manquantes, vérification des incohérences)
- Analyse univariée afin de comprendre la distribution de chaque variable
- Analyse bivariée pour étudier les relations entre les variables explicatives et la qualité du vin
- Étude des corrélations entre variables explicatives. Nous avons supprimé 2 variables car elles étaient fortement corrélées. (`free sulfur dioxide`, `density`)

Cette étape permet de mieux comprendre la structure des données et d’identifier les variables potentiellement explicatives de la qualité du vin.

---

## 2. Approche en régression

Une première analyse a été réalisée en considérant 3 groupes de qualité du vin :

- Estimation de modèles de régression
- Première évaluation des performances prédictives

Cette étape à eu de nombreuses difficultées à prédire la classe minoritaire (la classe 0), c'est pour cela qu'on est passé à une variable binaire.

---

## 3. Passage à une classification binaire

Dans un second temps, la variable cible a donc été transformée en une variable binaire (vin de bonne qualité vs vin de faible qualité).

Cela permet :
- de simplifier l’interprétation des résultats
- de répondre à une problématique plus concrète de décision

---

## 4. Modélisation

Mise en œuvre et comparaison de plusieurs modèles :

- Régression/logistique (modèle linéaire)
- Random Forest
- SVM 

---

## 6. Optimisation des hyperparamètres

Recherche des meilleurs paramètres (kernel, C, gamma pour les SVM).

---

## 7. Évaluation des performances

-Accuracy: elle mesure le taux de bonnes prédictions global.
-Le F1-score: elle permet d'évaluer la performance du modèle sur chaque classe en tenant compte des erreurs.
-La matrice de confusion: elle montre quelles classes sont bien ou mal prédites.

  

---

# Interprétabilité et explicabilité

Au-delà des performances prédictives, ce projet accorde une importance particulière à l’interprétation des modèles :

- **Interprétation globale** : identification des variables les plus influentes sur la qualité du vin  
- **Interprétation locale** : analyse des prédictions individuelles  

Des méthodes d’explicabilité (comme SHAP) sont utilisées afin de mieux comprendre le comportement des modèles, notamment celui des SVM souvent considérés comme des modèles peu interprétables.

---


# Problématique

La problématique centrale du projet peut être formulée ainsi :

> *Dans quelle mesure les caractéristiques d’un vin permettent-elles d’expliquer puis de prédire sa qualité ?*

# Résultat

Les deux éléments les plus importants sont la quantité d’alcool (plus il y en a meilleure est la qualité) et l’acidité (plus elle est élevée, moins le vin est bon).

D’autres éléments comme le sel ou le sucre  ont aussi un effet mais il est moins important.

En revanche, le pH du vin n’ont presque pas d’impact sur la qualité.

En résumé, certaines caractéristiques du vin permettent assez bien d’expliquer sa qualité, même si tout ne peut pas être parfaitement prédit, car d’autres éléments ont moins d’influence sur la qualité


# Ce qui n'a pas marché

- Les différents modèles testés en classification initiale n’ont pas permis de prédire correctement la classe 0. En effet, les performances étaient très faibles sur cette classe, sûrement en raison d’un déséquilibre entre les observations.Face à cette difficulté, nous avons choisi de regrouper les modalités de la variable cible en deux catégories plus équilibrées (faible qualité vs bonne qualité). Cette transformation a permis d’améliorer significativement les performances des modèles et leur capacité de prédiction.


# Ce qui à réussi




