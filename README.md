# Automatisation de la classification d'articles pour une marketplace

## Contexte

Classification automatique des articles d’une marketplace e-commerce anglophone à partir de leur image et description.  
L’objectif est d’automatiser la catégorisation, actuellement réalisée manuellement par les vendeurs.

## Objectifs

### Étape 1 – Faisabilité à partir du texte  
Notebook : `Sole_Johanna_1a_notebook_faisabilite_texte_042025.ipynb`  

- Analyse des données textuelles (catégories, caractéristiques linguistiques)  
- Prétraitement : nettoyage, normalisation, suppression des stopwords, lemmatisation  
- Extraction de features : Bag-of-Words, TF-IDF, Word2Vec, BERT, Universal Sentence Encoder  
- Réduction de dimension (PCA, t-SNE)  
- Clustering (K-Means) et évaluation (Homogeneity, Completeness, V-Measure, Adjusted Rand Index, Silhouette Score)  

### Étape 2 – Faisabilité à partir des images  
Notebook : `Sole_Johanna_1b_notebook_faisabilite_images_042025.ipynb`  

- Prétraitement et exploration des images  
- Extraction de caractéristiques visuelles : SIFT + Bag of Visual Words, réseaux pré-entraînés (VGG16, ResNet50, EfficientNetB0)  
- Réduction de dimension (PCA, t-SNE)  
- Clustering (K-Means) et évaluation avec mêmes métriques que pour le texte  

### Étape 3 – Classification supervisée à partir des images  
Notebook : `Sole_Johanna_2_notebook_classification_042025.ipynb`  

- Préparation des données : import, prétraitement, séparation train/validation/test  
- Modèle simple : MLP  
- Modèles avancés : CNN basique, EfficientNetB0, data augmentation  
- Évaluation des performances  

### Étape 4 – Collecte de nouveaux produits via API OpenFoodFacts  
Notebook : `Sole_Johanna_3_notebook_openfoodfacts_042025.ipynb`  

- Collecte de produits liés au champagne via l’API OpenFoodFacts  
- Extraction des 10 premiers produits dans un fichier CSV avec colonnes :  
  - foodId  
  - label  
  - category  
  - foodContentsLabel  
  - image  
- Script automatisé et reproductible  

## Résultat attendu

Automatisation fiable de la classification des articles par catégorie à partir du texte et des images, accompagnée d’une collecte automatisée de données produits via API.
