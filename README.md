# 🧬 Projet de Classification de Séquences ADN

## 🎯 Objectif
Ce projet vise à analyser des séquences d'ADN à l'aide de la **programmation orientée objet (POO)** et de **l'apprentissage automatique (Machine Learning)**. L'objectif est de prédire si une séquence est un **promoteur génétique** (`+`) ou non (`-`).

## 📁 Jeu de données
Les données proviennent de l'UCI Machine Learning Repository et contiennent **100 séquences ADN**. Chaque séquence contient exactement **57 nucléotides** (`A`, `T`, `C`, `G`) et une étiquette (`+` ou `-`).

## 🛠️ Technologies utilisées
- Python
- Google Colab
- Pandas, NumPy
- scikit-learn
- Matplotlib, Seaborn

## ⚙️ Architecture orientée objet
### 1. `DNASequence`
- Représente une séquence ADN.
- Méthode : `one_hot_encode()` — encode chaque nucléotide en vecteur binaire.

### 2. `ModelTrainer`
- Entraîne un modèle de classification (RandomForest).
- Évalue la performance via accuracy et classification report.

## 📊 Méthodologie
1. Chargement du dataset (`dna_sequences.csv`)
2. Transformation des séquences ADN en vecteurs numériques (one-hot encoding)
3. Création d'objets `DNASequence`
4. Entraînement de modèles (Random Forest)
5. Évaluation des résultats (accuracy, precision, recall...)

## 📈 Résultats
Le modèle Random Forest a atteint une précision d’environ **XX%** (à remplacer après exécution).  
Les séquences promoteurs montrent des motifs spécifiques détectables.

## 🧪 Exemple de code

```python
seq = DNASequence("ATGCGTACGTAGCTAGCTA", "+")
encoded = seq.one_hot_encode()
print(encoded[:20])
