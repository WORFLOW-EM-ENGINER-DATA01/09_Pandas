# TP : Tableaux Croisés Dynamiques avec Pandas

### Objectif
Apprendre à utiliser les tableaux croisés dynamiques (pivot tables) pour analyser et résumer des données à l'aide de Pandas.

### Pré-requis
- Connaissances de base en Python.
- Connaissances de base en Pandas.
- Installation de Pandas (`pip install pandas`).

### Dataset
Vous utiliserez un dataset fictif sur les ventes de produits dans différentes régions et par différents vendeurs.

### Étapes du TP

1. **Chargement des Données**
2. **Création de Tableaux Croisés Dynamiques**
3. **Analyse des Données**
4. **Questions d'Exercice**

### Étape 1 : Chargement des Données

Créez un DataFrame à partir des données suivantes :

```python
import pandas as pd

data = {
    'Region': ['North', 'South', 'East', 'West', 'North', 'South', 'East', 'West', 'North', 'South', 'East', 'West'],
    'Product': ['A', 'A', 'A', 'A', 'B', 'B', 'B', 'B', 'C', 'C', 'C', 'C'],
    'Sales': [150, 200, 300, 400, 350, 400, 250, 500, 200, 300, 400, 600],
    'Seller': ['John', 'Alice', 'Bob', 'Jane', 'John', 'Alice', 'Bob', 'Jane', 'John', 'Alice', 'Bob', 'Jane']
}

df = pd.DataFrame(data)
print(df)
```

### Étape 2 : Création de Tableaux Croisés Dynamiques

#### 2.1 Tableau croisé dynamique simple

Créez un tableau croisé dynamique qui résume les ventes totales par région et par produit.

```python
pivot1 = pd.pivot_table(df, values='Sales', index='Region', columns='Product', aggfunc='sum')
print(pivot1)
```

#### 2.2 Ajout des totaux

Ajoutez des marges pour obtenir les totaux des ventes par région et par produit.

```python
pivot2 = pd.pivot_table(df, values='Sales', index='Region', columns='Product', aggfunc='sum', margins=True, margins_name='Total')
print(pivot2)
```

#### 2.3 Analyse par vendeur

Créez un tableau croisé dynamique qui montre la moyenne des ventes par vendeur et par produit.

```python
pivot3 = pd.pivot_table(df, values='Sales', index='Seller', columns='Product', aggfunc='mean')
print(pivot3)
```

### Étape 3 : Analyse des Données

#### 3.1 Vente moyenne par région

Créez un tableau croisé dynamique qui montre la moyenne des ventes par région.

```python
pivot4 = pd.pivot_table(df, values='Sales', index='Region', aggfunc='mean')
print(pivot4)
```

#### 3.2 Vente totale par vendeur et par région

Créez un tableau croisé dynamique qui montre la somme des ventes par vendeur et par région.

```python
pivot5 = pd.pivot_table(df, values='Sales', index='Seller', columns='Region', aggfunc='sum', margins=True, margins_name='Total')
print(pivot5)
```

### Étape 4 : Questions d'Exercice

Répondez aux questions suivantes en utilisant les tableaux croisés dynamiques créés :

1. Quelle région a généré le plus de ventes pour le produit B ?
2. Quel vendeur a la moyenne de ventes la plus élevée pour le produit C ?
3. Quelle est la somme totale des ventes pour tous les produits dans la région East ?
4. Quel est le total des ventes de tous les vendeurs combinés ?
5. Quelle est la région avec la plus grande différence de ventes entre les produits A et B ?

### Solutions aux Questions d'Exercice

1. Utilisez `pivot2` pour répondre à la question.
2. Utilisez `pivot3` pour répondre à la question.
3. Utilisez `pivot1` avec la région East pour répondre à la question.
4. Utilisez `pivot5` pour répondre à la question.
5. Utilisez `pivot2` pour calculer la différence entre les ventes des produits A et B pour chaque région.
