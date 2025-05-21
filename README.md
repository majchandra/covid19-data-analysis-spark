🌍 Analyse Big Data & Machine Learning des cas COVID-19 avec PySpark  
Ce projet s’inscrit dans un contexte de traitement massif de données sur les cas confirmés de COVID-19 à l’échelle mondiale. Il met en œuvre les techniques de Machine Learning et de traitement distribué avec Apache Spark (via PySpark), afin de répondre à des requêtes analytiques complexes à partir d’un jeu de données volumineux et cumulatif.

---

🧠 Objectifs  
- Appliquer des techniques de Machine Learning sur des données Big Data  
- Utiliser PySpark pour le traitement parallèle et distribué  
- Répondre à 3 requêtes analytiques :
  1. Moyenne quotidienne des cas confirmés par pays et par mois  
  2. Moyenne, écart-type, min et max des cas par semaine et par continent  
  3. Clustering mensuel des pays les plus touchés avec **K-means**

---

🗃️ Données utilisées  
- Données COVID-19 cumulées (01/2020 à 03/2023)  
- 289 lignes × 1147 colonnes (dates, pays, coordonnées géographiques)  
- Prétraitement :
  - Transformation du format large → long (via `unpivot`)  
  - Ajout de colonnes : `Date`, `Continent`, `Year`, `Month`, `Week`, `Positive Cases`  
  - Nettoyage : suppression des lignes de croisières, traitement des incohérences temporelles

---

🛠️ Méthodologie  
- **Nettoyage de données** : suppression des valeurs manquantes ou erronées (coordonnées nulles, valeurs négatives, etc.)  
- **Feature engineering** :
  - Colonnes temporelles (`Year`, `Month`, `Week`, etc.)
  - Calcul des cas positifs journaliers
  - Attribution des continents à chaque pays  
- **Utilisation de PySpark SQL et MLlib** pour les agrégations et le clustering  
- Requêtes optimisées avec des fonctions Spark distribuées

---

📊 Requêtes traitées

**Query 1 — Par pays et par mois :**  
Calcul de la moyenne quotidienne des cas confirmés → représentation par histogrammes pour 8 pays clés (2020–2021)

**Query 2 — Par continent et par semaine :**  
Calcul des statistiques (moyenne, min, max, écart-type) pour les 100 pays les plus touchés → représentation par courbes

**Query 3 — Clustering K-means mensuel :**  
Segmentation des 50 pays les plus affectés chaque mois → visualisation sur cartes du monde, regroupés par couleur (cluster)

---

⏱️ Temps de traitement
- Prétraitement complet : 99 sec  
- Query 1 : 0.14 sec (agrégations simples)  
- Query 2 : 0.30 sec (régression linéaire incluse)  
- Query 3 : 170.8 sec (calculs + clustering)  
> ⚡ Le projet démontre la puissance de Spark dans le traitement efficace de grands volumes de données.

---

📚 Technologies utilisées  
- 🔥 Apache Spark (PySpark)  
- 🐍 Python, Pandas  
- 📦 Scikit-learn (régression linéaire)  
- 🧪 MLlib (clustering K-means)  
- 📊 Matplotlib, Seaborn  
- 📝 Jupyter Notebook

---

📝 Conclusion  
Ce projet démontre la pertinence de Spark pour traiter efficacement des données de santé massives et complexes.  
Les résultats des 3 requêtes sont conformes aux tendances réelles de la pandémie de COVID-19 entre 2020 et 2023.  
Une prochaine étape serait l’automatisation de ces analyses avec des données mises à jour quotidiennement, ou la comparaison des temps de traitement avec une approche basée uniquement sur Pandas.

