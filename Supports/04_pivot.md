# Tableaux Croisés Dynamiques (Pivot Tables)

Les tableaux croisés dynamiques, ou **pivot tables** en anglais, sont un outil puissant pour résumer, analyser, explorer et présenter des données. En utilisant les tableaux croisés dynamiques dans Pandas, vous pouvez transformer des données volumineuses en résumés faciles à comprendre.

## Pourquoi utiliser des tableaux croisés dynamiques ?

Les tableaux croisés dynamiques permettent de :
- **Synthétiser** les données de manière concise.
- **Comparer** différentes catégories et sous-catégories.
- **Repérer** les tendances et les anomalies.
- **Effectuer des calculs** personnalisés rapidement.

## Création d'un tableau croisé dynamique avec Pandas

En Pandas, la méthode `pivot_table` permet de créer des tableaux croisés dynamiques de manière simple et efficace.

### Exemple de base

Imaginons que vous disposez d'un DataFrame contenant des informations sur les ventes de produits dans différentes régions.

```python
import pandas as pd

data = {
    'Region': ['North', 'South', 'East', 'West', 'North', 'South', 'East', 'West'],
    'Product': ['A', 'A', 'A', 'A', 'B', 'B', 'B', 'B'],
    'Sales': [150, 200, 300, 400, 350, 400, 250, 500]
}

df = pd.DataFrame(data)
```

Pour créer un tableau croisé dynamique qui résume les ventes par région et par produit, vous pouvez utiliser la fonction `pivot_table` comme suit :

```python
pivot_table = pd.pivot_table(df, values='Sales', index='Region', columns='Product', aggfunc='sum')
print(pivot_table)
```

### Paramètres principaux de `pivot_table`

- **`values`** : La colonne à agréger.
- **`index`** : Les colonnes à utiliser comme index des lignes du tableau.
- **`columns`** : Les colonnes à utiliser comme en-têtes de colonnes du tableau.
- **`aggfunc`** : La fonction d'agrégation à appliquer (par exemple `sum`, `mean`, `count`, etc.).

### Avantages des tableaux croisés dynamiques

- **Flexibilité** : Vous pouvez facilement réorganiser et résumer vos données en modifiant les paramètres de `pivot_table`.
- **Polyvalence** : Les tableaux croisés dynamiques peuvent être utilisés pour une large gamme d'analyses, qu'il s'agisse de simples résumés de données ou de calculs plus complexes.
- **Lisibilité** : Ils offrent une présentation claire et concise des données, facilitant ainsi l'interprétation des résultats.

### Exemple avancé

Pour ajouter un niveau de complexité, vous pouvez calculer la moyenne des ventes par région et par produit, et ajouter une marge pour obtenir des totaux globaux.

```python
pivot_table = pd.pivot_table(df, values='Sales', index='Region', columns='Product', aggfunc='mean', margins=True, margins_name='Total')
print(pivot_table)
```

## Illustration 

Pour illustrer comment les tableaux croisés dynamiques (pivot tables) fonctionnent dans Pandas, voici un schéma simple. Le schéma montre comment les données d'un DataFrame sont transformées en un tableau croisé dynamique.

### Schéma : Transformation des Données en Tableau Croisé Dynamique

1. **Données Originales : DataFrame**

| Region | Product | Sales |
|--------|---------|-------|
| North  | A       | 150   |
| South  | A       | 200   |
| East   | A       | 300   |
| West   | A       | 400   |
| North  | B       | 350   |
| South  | B       | 400   |
| East   | B       | 250   |
| West   | B       | 500   |

2. **Configuration du Tableau Croisé Dynamique**
   - **Index** : `Region`
   - **Columns** : `Product`
   - **Values** : `Sales`
   - **Aggfunc** : `sum`

3. **Tableau Croisé Dynamique : Résumé des Ventes**

| Product | A   | B   | Total (Marges) |
|---------|-----|-----|----------------|
| Region  |     |     |                |
| North   | 150 | 350 | 500            |
| South   | 200 | 400 | 600            |
| East    | 300 | 250 | 550            |
| West    | 400 | 500 | 900            |
| **Total** | **1050** | **1500** | **2550** |

### Explication du Schéma

1. **Données Originales** : Le DataFrame initial contient des informations sur les ventes de produits dans différentes régions.

2. **Configuration du Tableau Croisé Dynamique** :
   - Les **lignes** (index) du tableau croisé sont les régions.
   - Les **colonnes** du tableau croisé sont les produits.
   - Les **valeurs** à agréger sont les ventes.
   - La fonction d'agrégation choisie est `sum`, ce qui signifie que les ventes seront additionnées pour chaque combinaison de région et de produit.

3. **Tableau Croisé Dynamique Résumé** :
   - Les cellules du tableau contiennent les ventes totales pour chaque combinaison de région et de produit.
   - Les totaux pour chaque région et chaque produit sont également calculés et affichés grâce aux marges (Total).

### Représentation Visuelle du Schéma

Voici une représentation visuelle du schéma :

```plaintext
Données Originales           Configuration          Tableau Croisé Dynamique
┌────────┬────────┬───────┐   ┌──────────────┐      ┌─────────┬─────┬─────┬───────┐
| Region | Product| Sales |   | Index: Region|      | Product |  A  |  B  | Total |
├────────┼────────┼───────┤   | Columns:     |      ├─────────┼─────┼─────┼───────┤
| North  |   A    |  150  |   | Product      |      | Region  |     |     |       |
| South  |   A    |  200  |   | Values: Sales|      |---------|-----|-----|-------|
| East   |   A    |  300  |   | Aggfunc: sum |      | North   | 150 | 350 |  500  |
| West   |   A    |  400  |   └──────────────┘      | South   | 200 | 400 |  600  |
| North  |   B    |  350  |                        | East    | 300 | 250 |  550  |
| South  |   B    |  400  |                        | West    | 400 | 500 |  900  |
| East   |   B    |  250  |                        |---------|-----|-----|-------|
| West   |   B    |  500  |                        | Total   |1050 |1500 | 2550  |
└────────┴────────┴───────┘                        └─────────┴─────┴─────┴───────┘
```

Ce schéma aide à visualiser comment les données sont transformées d'un format brut en un tableau croisé dynamique, facilitant ainsi l'analyse et la compréhension des données.