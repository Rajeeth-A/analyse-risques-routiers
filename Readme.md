# 🚗 Analyse des Accidents Corporels de la Circulation Routière en France

## 📌 Introduction
Ce projet analyse les **accidents corporels de la circulation routière en France** à l'aide de **PySpark** et **Python**. L'objectif est d'identifier les **facteurs de risque**, tels que :
- Les conditions atmosphériques 🌧️
- L'état de la route 🛣️
- Le type de collision 🚗💥
- Le type de route utilisée 🏎️

L'analyse repose sur des **techniques avancées de data science et de visualisation**, permettant de **mieux comprendre les causes des accidents et d'apporter des recommandations**.

---

## 📂 Source des Données
Les données proviennent du portail officiel **data.gouv.fr** :

🔗 **[Accidents Corporels de la Circulation Routière (2005 - 2023)](https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2023/)**

---

## 🛠️ Technologies Utilisées
- **Python 3.12** 🐍
- **PySpark** ⚡ (Initiation)
- **Pandas** (Manipulation des données)
- **Matplotlib & Seaborn** (Visualisation)
- **Folium** (Cartographie interactive des clusters)
- **K-Means (PySpark MLlib)** (Clustering des zones accidentogènes)

---

## 🔍 Analyse Réalisée
### 1️⃣ **Exploration et Nettoyage des Données**
- Chargement et fusion des fichiers **caractéristiques**, **lieux**
- Vérification des valeurs manquantes et transformation des données

### 2️⃣ **Analyse Spécifique des Accidents**
- **Conditions Atmosphériques** 🌦️ : Impact de la pluie, neige, brouillard sur les accidents
- **État de la Surface** 🛣️ : Routes mouillées, verglacées, enneigées
- **Type de Collision** 🚗💥 : Chocs frontaux, par l'arrière, en chaîne
- **Type de Route** 🏎️ : Routes départementales, autoroutes, nationales

### 3️⃣ **Clustering des Zones Accidentogènes**
- Utilisation de **K-Means** pour identifier les zones les plus dangereuses
- Cartographie interactive des clusters avec **Folium** 🗺️

---

## 📊 Résultats Clés
- Les **routes départementales et communales** sont les plus accidentogènes  
- **Les collisions par l'arrière et les chocs latéraux** sont les plus fréquents  
- **Les conditions normales** et **Les routes normales** génèrent le plus d'accidents, suggérant un excès de confiance  

- Les résultats obtenus avec Folium semblent être en accord avec le site de la Sécurité routière **[Cartographie des accidents](https://www.onisr.securite-routiere.gouv.fr/cartographie-des-accidents-metropole-dom-tom/)**

---

## Améliorations Possibles

- Tester DBSCAN pour mieux identifier les anomalies dans les clusters
- Construire un dashboard interactif avec Streamlit pour visualiser les tendances

---
