# 🧬 TP POO - Analyse de Séquences ADN

Ce projet a été réalisé dans le cadre du TP de **Programmation Orientée Objet (POO)**, visant à appliquer des concepts d’analyse de données biologiques en Python à l’aide des bibliothèques **Pandas**, **Scikit-learn**, **NumPy**, **Matplotlib** et **Seaborn**.

---

## 📁 Jeu de Données Utilisé

- Le fichier de données `dna_sequences.csv` contient des séquences d’ADN sous forme de lettres (`A`, `C`, `G`, `T`).
- Chaque ligne du fichier représente une séquence génétique, avec une **classe cible** (`+` ou `-`) indiquant une certaine condition biologique (par exemple : sain vs malade, ou présent vs absent).
- Exemple de structure :
  ```
  A,C,G,T,T,G,C,A,...,Class
  ```

---

## 🧱 Structure du Code

Le projet repose sur deux classes :

### `DNASequence`
- Représente une seule séquence ADN.
- Méthode principale : `one_hot_encode()` pour encoder la séquence en vecteurs binaires.
  - `A` → [1, 0, 0, 0]
  - `C` → [0, 1, 0, 0]
  - `G` → [0, 0, 1, 0]
  - `T` → [0, 0, 0, 1]

### `DNAAnalyzer`
- Gère l’ensemble du processus :
  - Chargement et exploration des données
  - Prétraitement et encodage
  - Entraînement du modèle Random Forest
  - Évaluation du modèle
  - Visualisation des classes

---

## ⚙️ Fonctionnalités

- 🔍 **Exploration des données** :
  - Affichage des premières lignes du fichier
  - Statistiques descriptives
  - Détection des valeurs manquantes

- 🧬 **Encodage One-Hot** :
  - Conversion des lettres ADN en vecteurs binaires adaptés à un algorithme de machine learning.

- 📊 **Modélisation** :
  - Utilisation de `RandomForestClassifier` pour entraîner un modèle de classification supervisée.

- 📈 **Évaluation et visualisation** :
  - Affichage de l’accuracy
  - Rapport détaillé (précision, rappel, F1-score)
  - Graphique des classes avec Seaborn

---

## ▶️ Instructions pour l’Exécution

1. Installer les bibliothèques nécessaires :
```bash
pip install pandas numpy seaborn scikit-learn matplotlib
```

2. Placer `tp_poo_dna.py` et `dna_sequences.csv` dans le même dossier.

3. Lancer le fichier Python :
```bash
python tp_poo_dna.py
```

---

## 🧪 Explication Détaillée des Résultats

### 🎯 Accuracy
- Affiche le **pourcentage de bonnes prédictions** faites par le modèle.
- Ex : `Accuracy: 0.92` signifie que 92% des séquences de test ont été correctement classées.

### 📋 Rapport de Classification (`classification_report`)
Ce rapport fournit pour chaque classe :

- **Precision** : parmi toutes les fois où le modèle a prédit cette classe, combien étaient correctes ?
- **Recall** : parmi tous les cas réels de cette classe, combien ont été retrouvés par le modèle ?
- **F1-score** : moyenne harmonique entre precision et recall.
- **Support** : nombre d’exemples de chaque classe dans les données de test.

Exemple :
```
              precision    recall  f1-score   support

           0       0.90      0.92      0.91        50
           1       0.94      0.92      0.93        60
```
👉 Cela signifie :
- Classe `0` (par exemple `-`) a une précision de 90% et un rappel de 92%.
- Classe `1` (par exemple `+`) a une meilleure performance.

### 📊 Graphique des Classes
- Le graphique en barres généré par `Seaborn` montre la **répartition des classes** dans le jeu de données.
- Cela permet de savoir si les données sont équilibrées ou déséquilibrées (important pour la qualité du modèle).

---

## 📌 À noter
- Vous pouvez modifier `random_state=42` dans le code pour obtenir un autre découpage des données (utile pour validation croisée).
- Pour tester d’autres modèles, vous pouvez remplacer `RandomForestClassifier()` par d’autres classifieurs de `scikit-learn`.

---

## 👨‍💻 Auteur
- Projet réalisé par [Benmeggoura Rahma , Azara Norhane , Laraba Noureddine] – Master Bioinformatique 2024–2025
- Dans le cadre du TP de Programmation Orientée Objet
