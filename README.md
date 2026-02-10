# 🚗 Car Model Acceptance Prediction

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)]()

Ce projet propose une analyse comparative de modèles d'apprentissage supervisé pour évaluer l'acceptabilité de véhicules (UCI Car Evaluation Dataset). L'étude confronte les **Arbres de Décision** classiques aux méthodes ensemblistes (**Random Forest** et **Gradient Boosting**) sur des tâches de classification multiclasse et binaire.

## 📋 Description du Projet

L'objectif est de prédire la classe d'un véhicule (`unacc`, `acc`, `good`, `vgood`) ou de recommander son achat (`No`, `Yes`) en fonction de 6 caractéristiques : prix d'achat, coût d'entretien, nombre de portes, capacité, taille du coffre et sécurité.

### Méthodologie
1.  **Prétraitement** : Encodage des variables ordinales (OrdinalEncoder) et gestion des classes déséquilibrées.
2.  **Modélisation** :
    * *Decision Tree* (Baseline)
    * *Random Forest* (Bagging)
    * *Gradient Boosting* (Boosting)
3.  **Optimisation** : Recherche d'hyperparamètres pour maximiser le Rappel et l'Accuracy.

---

## 📊 Résultats Clés

### 1. Classification Multiclasse (4 catégories)
Le **Gradient Boosting** s'impose comme le modèle le plus performant, surpassant l'arbre de décision et le Random Forest, notamment sur la détection des classes rares.

| Modèle | Accuracy Globale | Rappel (`vgood`) | Observation |
| :--- | :---: | :---: | :--- |
| **Decision Tree** | ~91.00% | 0.90 | Difficultés à généraliser sur les données complexes. |
| **Random Forest** | 98.00% | 0.90 | Très robuste, excellente précision globale. |
| **Gradient Boosting** | **98.84%** | **1.00** | **Meilleur Modèle**. Capture 100% des véhicules "Very Good". |

### 2. Classification Binaire (Recommandation : No / Yes)
Le défi principal est le fort déséquilibre des classes (479 `No` vs 40 `Yes` dans le jeu de test).

* **Random Forest** : Le choix de la **sécurité**.
    * **Précision : 1.00** (Aucun Faux Positif).
    * Si ce modèle recommande une voiture, elle est assurément bonne.
* **Gradient Boosting** : Le choix de la **performance**.
    * **Accuracy : 95.18%**.
    * Meilleur compromis pour minimiser les Faux Négatifs (voitures ratées).
* **Decision Tree** :
    * Précision faible (**0.44**), générant trop de fausses recommandations.

---

## 🛠️ Installation et Utilisation

### Prérequis
* Python 3.x
* Bibliothèques : `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

### Instructions
1.  **Cloner le dépôt** :
    ```bash
    git clone [https://github.com/votre-user/CarModelAcceptance-Ensemble.git](https://github.com/votre-user/CarModelAcceptance-Ensemble.git)
    cd CarModelAcceptance-Ensemble
    ```

2.  **Installer les dépendances** :
    ```bash
    pip install -r requirements.txt
    # Ou manuellement : pip install pandas scikit-learn seaborn matplotlib
    ```

3.  **Lancer l'analyse** :
    Ouvrez le notebook Jupyter ou exécutez le script principal pour reproduire les entraînements et visualiser les matrices de confusion.

---

## 📈 Conclusion

Cette étude démontre la supériorité des méthodes ensemblistes sur ce jeu de données :
* Utilisez le **Gradient Boosting** si la priorité est de ne manquer aucune opportunité (Rappel maximal).
* Utilisez le **Random Forest** si la priorité est d'éviter absolument une mauvaise recommandation (Précision maximale).

---
*Projet réalisé dans le cadre du module d'Apprentissage Supervisé.*
