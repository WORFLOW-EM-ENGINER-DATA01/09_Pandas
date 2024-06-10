# Matrices dans Pandas

## 3.1 Qu'est-ce qu'une Matrice ?

En informatique, une matrice est un tableau rectangulaire de valeurs organisées en lignes et en colonnes. Pandas utilise la structure `DataFrame` pour manipuler des matrices.

## 3.2 Création d'une Matrice

### 3.2.1 À partir d'une liste de listes

Vous pouvez créer une matrice en utilisant une liste de listes. Chaque sous-liste représente une ligne de la matrice.

```python
import pandas as pd

data = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

matrix = pd.DataFrame(data)
print(matrix)
```

### 3.2.2 À partir d'un dictionnaire de listes

Chaque clé du dictionnaire représente une colonne, et la liste correspondante représente les valeurs de cette colonne.

```python
data = {
    'Col1': [1, 4, 7],
    'Col2': [2, 5, 8],
    'Col3': [3, 6, 9]
}

matrix = pd.DataFrame(data)
print(matrix)
```

## 3.3 Opérations sur les Matrices

### 3.3.1 Sélection des Éléments

#### Par indices

Pour sélectionner un élément spécifique, utilisez la méthode `.iloc`.

```python
# Sélectionner l'élément à la première ligne et deuxième colonne
element = matrix.iloc[0, 1]
print(element)  # Sortie: 2
```

#### Par étiquettes

Si votre DataFrame a des étiquettes, utilisez la méthode `.loc`.

```python
# Sélectionner l'élément dans la colonne 'Col2' et la première ligne
element = matrix.loc[0, 'Col2']
print(element)  # Sortie: 2
```

### 3.3.2 Sélection de Sous-Matrices

Pour sélectionner une sous-matrice, utilisez des tranches (`slices`).

```python
# Sélectionner les deux premières lignes et les deux premières colonnes
sub_matrix = matrix.iloc[:2, :2]
print(sub_matrix)
```

### 3.3.3 Opérations Mathématiques

Vous pouvez effectuer des opérations mathématiques sur les matrices.

#### Addition

```python
matrix_add = matrix + 10
print(matrix_add)
```

#### Multiplication

```python
matrix_mul = matrix * 2
print(matrix_mul)
```

#### Somme des colonnes ou des lignes

```python
# Somme de chaque colonne
col_sum = matrix.sum(axis=0)
print(col_sum)

# Somme de chaque ligne
row_sum = matrix.sum(axis=1)
print(row_sum)
```

### 3.3.4 Transposition

La transposition d'une matrice échange ses lignes et ses colonnes.

```python
matrix_transposed = matrix.T
print(matrix_transposed)
```

### 3.3.5 Produit Matriciel

Pour effectuer le produit matriciel (multiplication de matrices), utilisez la méthode `.dot`.

```python
matrix1 = pd.DataFrame([[1, 2], [3, 4]])
matrix2 = pd.DataFrame([[5, 6], [7, 8]])

product_matrix = matrix1.dot(matrix2)
print(product_matrix)
```

## 3.4 Manipulation Avancée

### 3.4.1 Ajout et Suppression de Lignes et Colonnes

#### Ajouter une Colonne

```python
matrix['Col4'] = [10, 11, 12]
print(matrix)
```

#### Ajouter une Ligne

```python
new_row = pd.DataFrame([[10, 11, 12, 13]], columns=matrix.columns)
matrix = pd.concat([matrix, new_row], ignore_index=True)
print(matrix)
```

#### Supprimer une Colonne

```python
matrix.drop('Col4', axis=1, inplace=True)
print(matrix)
```

#### Supprimer une Ligne

```python
matrix.drop(3, axis=0, inplace=True)
print(matrix)
```

### 3.4.2 Appliquer des Fonctions

Vous pouvez appliquer des fonctions à chaque élément, ligne ou colonne.

#### Appliquer une fonction à chaque élément

```python
matrix_applied = matrix.applymap(lambda x: x ** 2)
print(matrix_applied)
```

#### Appliquer une fonction à chaque colonne

```python
matrix_applied = matrix.apply(lambda col: col + 5)
print(matrix_applied)
```

## 3.5 Exercice Pratique

### Exercice : Manipulation de Matrices

1. Créez une matrice 3x3 avec des valeurs de 1 à 9.
2. Ajoutez une colonne 'Col4' avec les valeurs [10, 11, 12].
3. Multipliez chaque élément de la matrice par 3.
4. Calculez la somme de chaque colonne.
