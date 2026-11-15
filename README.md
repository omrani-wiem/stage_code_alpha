# stage_code_alpha
# Credit Scoring & Risk Prediction

Projet de Machine Learning réalisé dans le cadre d'un stage chez **CodeAlpha**, visant à prédire et évaluer le risque de crédit bancaire à partir du jeu de données *German Credit Data*.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/omrani-wiem/stage_code_alpha/blob/main/stage_code_alpha.ipynb)

## 📋 Aperçu du projet

L'objectif de ce projet est de construire un pipeline complet de classification supervisée capable d'estimer le niveau de risque associé à une demande de crédit en fonction du profil socio-économique de l'emprunteur et des caractéristiques du prêt.

## 📊 Jeu de données

* **Source :** [German Credit Data (Kaggle)](https://www.kaggle.com/datasets/mdaliraza/german-credit-data)
* **Volume :** 1 000 observations et 9 variables explicatives :
  * **Variables démographiques & professionnelles :** `Age`, `Sex`, `Job`, `Housing`
  * **Variables financières :** `Saving accounts`, `Checking account`, `Credit amount`, `Duration`, `Purpose`
* **Variable cible (`Risk`) :** Variable binaire créée à partir de la médiane du montant du crédit (`Credit amount`).

## ⚙️ Méthodologie & Pipeline

1. **Acquisition des données :** Téléchargement automatisé via l'API Kaggle sous Google Colab.
2. **Prétraitement & Feature Engineering :**
   * Suppression des colonnes d'index superflues (`Unnamed: 0`).
   * Imputation des valeurs manquantes (`Saving accounts` et `Checking account`) par la modalité `'none'`.
   * Encodage One-Hot (`OneHotEncoder` via `ColumnTransformer`) des variables catégorielles.
   * Standardisation (`StandardScaler`) des variables numériques.
3. **Analyse Exploratoire (EDA) :** Étude des corrélations entre les variables via une matrice thermique (*heatmap* Seaborn).
4. **Modélisation & Optimisation :**
   * Séparation entraînement / test (`train_test_split`).
   * Entraînement et réglage des hyperparamètres par validation croisée (`GridSearchCV`) sur trois modèles :
     * **Régression Logistique** (`LogisticRegression`)
     * **Arbre de Décision** (`DecisionTreeClassifier`)
     * **Forêt Aléatoire** (`RandomForestClassifier`)
5. **Évaluation :** Comparaison des modèles selon les métriques `Accuracy`, `Precision`, `Recall`, `F1-score`, `ROC-AUC` et la matrice de confusion.

## 🛠️ Technologies utilisées

* **Langage :** Python 3
* **Environnement :** Google Colab / Jupyter Notebook
* **Bibliothèques :** `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `kaggle`

## 🚀 Utilisation

1. Cloner le dépôt :
   ```bash
   git clone [https://github.com/omrani-wiem/stage_code_alpha.git](https://github.com/omrani-wiem/stage_code_alpha.git)
   cd stage_code_alpha
