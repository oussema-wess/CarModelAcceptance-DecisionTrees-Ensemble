# 🚗 Car Model Acceptance Prediction

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)]()

Ce projet propose une analyse comparative de modèles d'apprentissage supervisé pour évaluer l'acceptabilité de véhicules (UCI Car Evaluation Dataset). L'étude confronte les **Arbres de Décision** classiques aux méthodes ensemblistes (**Random Forest** et **Gradient Boosting**).

## 📂 Structure du Dépôt

Voici le contenu détaillé des fichiers du projet :

* **`Car_Evaluation_Classification.ipynb`** : Le notebook Jupyter principal contenant tout le code (nettoyage des données, entraînement des modèles, visualisations et résultats).
* **`car_excel.xlsx`** : Le jeu de données original utilisé pour l'entraînement.
* **`car_excel_bis.xlsx`** : Une version secondaire du jeu de données (sauvegarde ou variante).
* **`car_decision_tree_full.png`** : Une image haute résolution générée montrant la structure complète de l'arbre de décision entraîné.
* **`README.md`** : Ce fichier de documentation.

---

## 📊 Résultats Clés

### 1. Classification Multiclasse (4 catégories)
Le **Gradient Boosting** surpasse les autres modèles pour la détection des classes rares.

| Modèle | Accuracy Globale | Rappel (`vgood`) | Observation |
| :--- | :---: | :---: | :--- |
| **Decision Tree** | ~91.00% | 0.90 | Baseline, manque de stabilité. |
| **Random Forest** | 98.00% | 0.90 | Excellente précision globale. |
| **Gradient Boosting** | **98.84%** | **1.00** | **Meilleur Modèle**. Sans faute sur les meilleures voitures. |

### 2. Classification Binaire (Recommandation : No / Yes)
Sur un jeu de données déséquilibré (479 `No` vs 40 `Yes`) :

* **Random Forest** : **Précision de 1.00**. Il ne recommande que des valeurs sûres (0 Faux Positif).
* **Gradient Boosting** : **Accuracy de 95.18%**. Il capture davantage de bonnes voitures au prix de quelques erreurs mineures.

---

## 🛠️ Installation et Utilisation

### Prérequis
* Python 3.x
* Jupyter Notebook ou JupyterLab

### Instructions
1.  **Cloner le dépôt** :
    ```bash
    git clone [https://github.com/votre-user/CarModelAcceptance-Ensemble.git](https://github.com/votre-user/CarModelAcceptance-Ensemble.git)
    cd CarModelAcceptance-Ensemble
    ```

2.  **Installer les dépendances** :
    Les bibliothèques suivantes sont nécessaires (visibles dans les imports) :
    ```bash
    pip install pandas scikit-learn seaborn matplotlib openpyxl graphviz
    ```

3.  **Lancer l'analyse** :
    Ouvrez le fichier notebook pour exécuter le code :
    ```bash
    jupyter notebook Car_Evaluation_Classification.ipynb
    ```

---

## 📈 Conclusion

Cette étude démontre la supériorité des méthodes ensemblistes :
* Privilégiez le **Gradient Boosting** pour maximiser la détection des opportunités (Rappel).
* Privilégiez le **Random Forest** pour une fiabilité absolue dans les recommandations (Précision).

---
*Projet réalisé dans le cadre du module d'Apprentissage Supervisé.*
