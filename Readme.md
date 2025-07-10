# Analyse des Accidents Corporels de la Circulation Routière en France (2005-2023)

> **Contexte**  
Chaque année, des milliers d’accidents corporels surviennent sur les routes françaises. Ce projet vise à **identifier les principaux facteurs de risque**, à **cartographier les zones accidentogènes** et à **proposer des pistes d’amélioration** basées sur les données publiques de la Sécurité Routière. Cette étude exploite ~1,2 million d’accidents corporels survenus en France métropolitaine entre 2005 et 2023 afin d’identifier les facteurs de risque et de cartographier les zones les plus dangereuses.

---

## 1. Objectifs
1. **Quantifier** l’impact des conditions atmosphériques, de l’état de la chaussée, du type de collision et du type de route sur la fréquence des accidents.  
2. **Localiser** les « hot-spots » d’accidents grâce au clustering spatial.  
3. **Proposer** des recommandations factuelles aux acteurs de la sécurité routière.

---

## 2. Jeu de Données
| Source | Période | Volume | Variables clés |
|--------|---------|--------|----------------|
| [data.gouv.fr – Fichier accidents corporels](https://www.data.gouv.fr/fr/datasets/base-de-donnees-accidents-corporels-de-la-circulation/) | 2022 | 55000 accidents | météo, état de surface, localisation GPS, type de collision, etc. |

> **Granularité** : chaque enregistrement correspond à un accident impliquant au moins un blessé.

---

## 3. Stack Technique
- **Python 3.12** & **PySpark**
- **Pandas / NumPy**
- **Matplotlib & Seaborn**
- **Folium** – (apprentissage - et notions de GeoPandas)
- **K-Means**

---

## 4. Méthodologie

### 4.1 Ingestion & Nettoyage
- Fusion des tables *caractéristiques*, *lieux* et *usagers*  
- Vérification des valeurs manquantes

### 4.2 Analyse Exploratoire
| Facteur | Insight principal (2005-2023) |
|---------|------------------------------|
| **Conditions météo** | 90 % des accidents surviennent par temps **sec** |
| **État de surface** | Routes **mouillées** : 80% suface sèche VS 18 % Mouillé. |
| **Type de collision** | Chocs **Deux véhicules – par le côté** et **Autre collision** représentent **60 %** des collisions. |
| **Type de voie** | Routes **départementales / communales** = 79 % des accidents|

### 4.3 Clustering des « Hot-Spots »
1. **Agrégation** : accidents géolocalisés → latitude/longitude (résolution ≈ 100 m).  
2. **K-Means** (`k = 20`) pour regrouper les points denses.  
3. **Folium** : rendu interactif permettant de zoomer sur chaque cluster et d’afficher le profil de risque (conditions météo, type de voie, etc.).

---

## 5. Résultats Clés

| Indicateur | Valeur |
|------------|--------|
| **Accidents totaux analysés** | 55302 |
| **Hot-spots identifiés** | 20 clusters  |
| **Condition la plus risquée** | Temps Normal : Confiance des conducteurs |
| **Section de route la plus accidentogène** | Grandes villes |

---

## 6. Suggestion
1. **Renforcer l’éclairage** et la signalisation sur les tronçons départementaux identifiés.  
2. **Campagnes de sensibilisation** ciblant la distance de sécurité pour réduire les chocs arrière.  
3. **Revêtement drainant** ou traitement anti-aquaplaning sur les segments clusterisés Mouillé + Pluie.
