❤️ Classification des Maladies Cardiaques — Projet de Machine Learning

Auteure : Riham El Idrissi
Cours : Projet Final — Apprentissage Automatique
Dataset : Heart Disease — UCI Machine Learning Repository

📌 Présentation

Ce projet consiste à développer un modèle de classification binaire permettant de prédire la présence ou l'absence d'une maladie cardiaque chez des patients à partir de données cliniques.

Il couvre l’ensemble du pipeline de machine learning :

Exploration des données

Prétraitement

Entraînement des modèles

Évaluation

Optimisation

📊 Dataset
Propriété	Détails
Nom	Heart Disease
Source	UCI Machine Learning Repository
ID	45
Créateurs	Andras Janosi, William Steinbrunn, Matthias Pfisterer, Robert Detrano
Année	1989
DOI	10.24432/C52P4X

Le dataset contient des données cliniques pour chaque patient.

🎯 Variable cible

La variable num a été transformée en binaire :

0 → Absence de maladie cardiaque

1 → Présence de maladie cardiaque (valeurs 1 à 4 regroupées)

🧾 Variables
Variable	Description
age	Âge
sex	Sexe (1 = homme, 0 = femme)
cp	Type de douleur thoracique
trestbps	Pression artérielle au repos
chol	Cholestérol
fbs	Glycémie à jeun > 120
restecg	Résultats ECG
thalach	Fréquence cardiaque maximale
exang	Angine induite par l’effort
oldpeak	Dépression ST
slope	Pente ST
ca	Nombre de vaisseaux majeurs
thal	Type de thalassémie
📁 Structure du projet
El-Idrissi-Riham.ipynb
confusion_matrix.png
confusion_matrix_optimized.png
target_distribution.png
boxplots.png
correlation_heatmap.png
feature_importance.png
⚙️ Pipeline
🔍 1. Exploration des données

Chargement via ucimlrepo

Analyse des types et statistiques

Détection des valeurs manquantes (ca, thal)

Visualisations :

Distribution de la cible

Boxplots

Heatmap de corrélation

🧹 2. Prétraitement

Binarisation :

Transformation de num en variable binaire (0/1)

Gestion des valeurs manquantes :

ca → médiane

thal → mode

Encodage :

One-Hot Encoding (drop_first=True) :

sex, cp, fbs, restecg, exang, slope, thal

Normalisation :

StandardScaler appliqué aux variables numériques :

age, trestbps, chol, thalach, oldpeak, ca

Split :

Train/Test = 80/20

Stratification

random_state = 42

🤖 3. Modèle de base — Régression Logistique

LogisticRegression(max_iter=1000, class_weight='balanced')

Évaluation :

Accuracy

Classification report

Matrice de confusion

🌲 4. Modèle optimisé — Random Forest

RandomForestClassifier

Optimisation avec GridSearchCV (5-fold CV)

Hyperparamètres testés :

n_estimators : [50, 100]

max_depth : [None, 5, 10]

Validation croisée :

5 folds pour garantir la robustesse

Interprétabilité :

Importance des variables

📈 Résultats
Modèle	Précision
Régression Logistique	~85%
Random Forest (optimisé)	~90%
🔑 Points clés

Le modèle Random Forest atteint ~90% de précision

Bonne généralisation confirmée par validation croisée

Variables les plus importantes :

cp (douleur thoracique)

thalach (fréquence cardiaque max)

slope (pente ST)

🧰 Prérequis
pip install ucimlrepo scikit-learn matplotlib seaborn pandas numpy

Version Python : 3.12+

▶️ Instructions d'exécution

Cloner ou télécharger le dépôt

Installer les dépendances

Ouvrir El-Idrissi-Riham.ipynb dans Jupyter Notebook / JupyterLab

Exécuter toutes les cellules

📌 Remarque :
Le dataset est automatiquement téléchargé depuis le UCI Repository — aucune action manuelle requise.

🚀 Améliorations possibles

Test d'autres modèles (XGBoost, SVM)

Optimisation avancée (Random Search, Bayesian)

Déploiement en API (FastAPI / Flask)

Interface utilisateur (Streamlit)

⭐ Auteur

Riham El Idrissi
