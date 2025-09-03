# Projet Data Mining — E-commerce

## Contexte
Ce projet a été réalisé dans le cadre d’un **exposé de Master 1 IASD** dans l’unité d’enseignement **Data Mining**.  
L’objectif est d’appliquer les techniques de data mining pour **analyser la satisfaction client dans le e-commerce**, identifier les **moteurs d’insatisfaction** et proposer des **recommandations stratégiques**.

---

## Objectifs pédagogiques
- Comprendre le **cycle complet d’un projet de data mining** : prétraitement, EDA, modélisation, évaluation.  
- Appliquer des **méthodes de clustering** pour segmenter les clients.  
- Tester et comparer plusieurs **modèles de Machine Learning** :  
  - **Régression** : Linear Regression, RandomForest, GradientBoosting, TensorFlow DNN.  
  - **Classification** : Logistic Regression, RandomForest, GradientBoosting, TensorFlow DNN.  
- Identifier les **drivers clés** (qualité produit, livraison, service client, promos, fidélité).  
- Traduire les résultats en **recommandations business concrètes**.

---

## Contenu du projet

| Fichier | Description |
|---------|-------------|
| `Projet_DataMining_Ecommerce_FINAL.ipynb` | Notebook complet (EDA, clustering, modèles, drivers, recommandations) |
| `dataset/E-commerce_Dataset.csv` | Jeu de données e-commerce (clients, satisfaction, retours) |
| `Analyse Data Mining sur le e-commerce.pptx` | Diaporama PowerPoint de présentation |
| `README.md` | Présentation détaillée du projet, instructions et contexte |

---

## Méthodologie

1. **Exploration descriptive (EDA)**  
   - Histogrammes, distributions, corrélations.  
   - Premières tendances : retours plus élevés chez les clients utilisant beaucoup de réductions.  

2. **Segmentation (Clustering K-Means)**  
   - Choix du nombre de clusters via **méthode du coude** et **silhouette**.  
   - Projection PCA en 2D pour visualiser les clusters.  
   - Profils distincts : clients fidèles, sensibles aux promos, gros acheteurs, réguliers.  

3. **Modélisation — Régression**  
   - Évaluation via **MAE, RMSE, R²**.  
   - Résultat : R² faible → difficulté à prédire `ReturnRate`.  

4. **Modélisation — Classification**  
   - Évaluation via **Accuracy, Precision, Recall, F1, ROC-AUC**.  
   - RandomForest et GradientBoosting performants, Logistic Regression en baseline.  
   - Courbes ROC & PR pour comparer les modèles.  

5. **Analyse des drivers**  
   - Régression : importance de `ProductQualityRating`, `DeliveryTimeRating`, `CustomerServiceRating`.  
   - Classification : rôle majeur de `DiscountUsage`, `LoyaltyProgramMember`, `PurchaseAmount`.  
   - Graphiques barplot + permutation importance.  

6. **Recommandations stratégiques**  
   - **Produit** : renforcer le contrôle qualité et packaging.  
   - **Livraison** : réduire les délais et fiabiliser le suivi.  
   - **Service client** : améliorer SLA et temps de réponse.  
   - **Fidélité & UX** : cibler mieux les promotions, améliorer le site et l’app mobile.  

---

## Résultats clés
- La **classification** a fourni de meilleures performances que la régression.  
- Les **drivers identifiés** confirment l’importance de la qualité produit, de la livraison et du service client.  
- Les recommandations sont directement **actionnables** par une entreprise e-commerce.  

---

## Technologies utilisées
- **Python 3.x**
- **Pandas / NumPy**
- **Scikit-learn**
- **TensorFlow / Keras**
- **Matplotlib / Seaborn**
- **Jupyter Notebook**

---

## Perspectives
- Intégrer **plus de variables** (historique de navigation, avis clients).  
- Tester des modèles avancés (**XGBoost, LightGBM, AutoML**).  
- Utiliser des techniques de **Deep Learning séquentiel** (*RNN, LSTM*) pour modéliser l’historique d’achat.  
- Créer un **dashboard interactif** avec **Streamlit** ou **PowerBI** pour les décideurs.  

---


## Exécution du projet

### 1. Sur Google Colab (recommandé)
Ouvrir le notebook directement depuis GitHub dans Google Colab.  
Exemple :
```python
import pandas as pd

url = "https://raw.githubusercontent.com/<USERNAME>/<REPO>/main/data/E-commerce_Dataset.csv"
df = pd.read_csv(url)
df.head()
