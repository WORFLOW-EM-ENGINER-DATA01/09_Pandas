# TP : Tableaux Croisés Dynamiques avec Pandas


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


#### 2.2 Ajout des totaux

Ajoutez des marges pour obtenir les totaux des ventes par région et par produit.


#### 2.3 Analyse par vendeur

Créez un tableau croisé dynamique qui montre la moyenne des ventes par vendeur et par produit.



### Étape 3 : Analyse des Données

#### 3.1 Vente moyenne par région

Créez un tableau croisé dynamique qui montre la moyenne des ventes par région.


#### 3.2 Vente totale par vendeur et par région

Créez un tableau croisé dynamique qui montre la somme des ventes par vendeur et par région.


### Étape 4 : Questions d'Exercice

Répondez aux questions suivantes en utilisant les tableaux croisés dynamiques créés :

1. Quelle région a généré le plus de ventes pour le produit B ?
2. Quel vendeur a la moyenne de ventes la plus élevée pour le produit C ?
3. Quelle est la somme totale des ventes pour tous les produits dans la région East ?
4. Quel est le total des ventes de tous les vendeurs combinés ?
5. Quelle est la région avec la plus grande différence de ventes entre les produits A et B ?
