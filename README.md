# Projet 6 – Automatisation de la classification d'articles pour une marketplace

## 📌 Contexte

Vous êtes **Data Scientist** au sein de l’entreprise **"Place de marché"**, qui souhaite lancer une marketplace e-commerce anglophone.  
Sur cette plateforme, les vendeurs proposent des articles aux acheteurs en postant une **photo** et une **description**.

Actuellement, l’attribution de la **catégorie d’un article** est effectuée **manuellement** par les vendeurs, ce qui est **peu fiable** et difficilement **scalable**.  
Pour améliorer l’expérience utilisateur et préparer un passage à l’échelle, l’entreprise souhaite **automatiser cette tâche**.

Linda, Lead Data Scientist, vous confie la mission suivante :

- Étudier la **faisabilité d’un moteur de classification automatique** des articles, à partir de **leur image et leur description**.
- Réaliser ensuite une **classification supervisée** des images.
- Enfin, collecter des données de nouveaux produits via l'**API OpenFoodFacts** et automatiser leur extraction.

---

## 📝 Objectifs

### Étape 1 – Étude de faisabilité à partir du texte

Notebook : `Sole_Johanna_1a_notebook_faisabilite_texte_042025.ipynb`

Ce notebook explore la faisabilité d’une classification automatique basée sur les **descriptions textuelles** des articles.

Plan :

1. **Exploration des données textuelles** : analyse des catégories et caractéristiques linguistiques.
2. **Prétraitement du texte** : nettoyage, normalisation, suppression des stopwords, lemmatisation.
3. **Extraction de features** : 
   - Bag-of-Words
   - TF-IDF
   - Word2Vec
   - BERT
   - Universal Sentence Encoder
4. **Réduction de dimension et visualisation** (PCA, t-SNE).
5. **Clustering et évaluation quantitative** :
   - K-Means
   - Homogeneity, Completeness, V-Measure, Adjusted Rand Index, Silhouette Score.

👉 **But** : déterminer si le texte seul permet de regrouper les articles par catégorie.

---

### Étape 2 – Étude de faisabilité à partir des images

Notebook : `Sole_Johanna_1b_notebook_faisabilite_images_042025.ipynb`

Ce notebook explore la faisabilité d’une classification automatique basée sur les **images** des articles.

Plan :

1. **Prétraitement et exploration des images**.
2. **Extraction de caractéristiques visuelles** :
   - SIFT + Bag of Visual Words
   - Réseaux pré-entraînés : VGG16, ResNet50, EfficientNetB0.
3. **Réduction de dimension et visualisation** (PCA, t-SNE).
4. **Clustering et évaluation quantitative** (K-Means, mêmes métriques que pour le texte).

👉 **But** : vérifier si les images permettent de différencier les catégories d’articles.

---

### Étape 3 – Classification supervisée à partir des images

Notebook : `Sole_Johanna_2_notebook_classification_042025.ipynb`

Après avoir validé l’intérêt des features visuelles, ce notebook implémente une **classification supervisée**.

Plan :

1. **Préparation des données** : import, prétraitement, split train/val/test.
2. **Modèle de base** : simple MLP pour point de référence.
3. **Modèles avancés** :
   - EfficientNetB0.
   - **Data Augmentation**.
4. **Évaluation des performances**.

---

### Étape 4 – Collecte de nouveaux produits via API OpenFoodFacts

Notebook : `Sole_Johanna_3_notebook_openfoodfacts_042025.ipynb`

Objectif :

- Interroger l’**API OpenFoodFacts** pour collecter des produits liés au **champagne**.
- Extraire les **10 premiers produits** dans un fichier `.csv` avec les colonnes :
  - `foodId`
  - `label`
  - `category`
  - `foodContentsLabel`
  - `image`

👉 Fournir un script automatisé reproductible.

---

