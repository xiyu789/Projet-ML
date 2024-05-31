# ReadMe Projet Machine Learning
#### Xiyu XUE, Xinzhuo PENG

## Description du problématique

L'étude de la fraude bancaire revêt une importance, parce qu'elle aide à la protection des économies individuelles et des banques contre des pertes inattendues. De plus, elle joue un rôle essentiel dans la gestion du risque. Cette recherche permet également de renforcer la résilience du système financier face aux menaces croissantes.

Pour mener à bien cette étude, nous avons téléchargé une base de données de 1 million d'échantillons, accompagnés de 31 variables explicatives, à la fois numériques et catégorielles, depuis le site Kaggle.

Notre approche analytique débute par le prétraitement des données, qui consiste à éliminer les colonnes présentant des variables redondantes ou un nombre significatif de données manquantes. Les variables catégorielles sont ensuite transformées en valeurs binaires, représentant chaque catégorie par des valeurs de 0 ou 1. Pour l'analyse initiale, nous appliquons une régression logistique, suivie de l'utilisation du modèle K-means pour le clustering non supervisé et de la forêt aléatoire pour la modélisation supervisée. Par ailleurs, afin de réduire le nombre de variables explicatives et de diminuer le temps d'exécution, nous mettons en œuvre une Analyse en Composantes Principales (PCA).


### Data:
- `Base.xlsx`: Notre base de données pour ce projet "Bank Account Fraud Dataset Suite (NeurIPS 2022)", téléchargé via le site Kaggle. Ce base est générée par un GAN à partir d'un ensemble de données réel sur les fraudes aux comptes bancaires.
- Voici le lien: https://www.kaggle.com/datasets/sgpjesus/bank-account-fraud-dataset-neurips-2022/data

### Modules:
-  **Préparation et visualisation des données**: on montre d'abord les types de nos variables, et la distribution de notre résultats (défaut / ne pas défaut).
-  **Retraitement des données & Pré-processing**: dans cette partie là, on travaille sur la base, en supprimant des variables qui manquent une partie significative de data, analysant les corrélations entre variables, modifiant certains type de variables, etc.
-  **Training & Validation**: on commence par la préparation des données pour l'entraînement et la validation du modèle de détection de fraude. Les données sont normalisées, les variables catégorielles sont encodées, et les ensembles d'entraînement et de test sont créés en tenant compte du déséquilibre des classes. Ces préparations sont cruciales pour assurer que le modèle de machine learning puisse apprendre efficacement et être évalué de manière juste.

## Training & Validation

Dans cette partie là, on utilise différents modèles pour travailler sur ce sujet afin de trouver une solution optimale, et précise.

-  **Modèle Simple --- Régression Logistique** : Pour la phase initiale de modélisation, nous avons opté pour la régression logistique afin d'obtenir une première compréhension du traitement de ce sujet. Lors de l'initialisation du modèle, nous avons choisi l'option class_weight='balanced', permettant ainsi au classificateur d'ajuster automatiquement les poids des différentes classes pour éviter tout biais dans le modèle.
-  **Modèle Non-Supervisé --- Clustering** : Lorsqu'il n'y a pas de Y demandé, on applique d'abord le PCA analyse pour simplifier le modèle et ensuite on utilise K-Means clustering pour trouver la solution optimale.
-  **Modèle Supervisé --- Randome Forest** :
