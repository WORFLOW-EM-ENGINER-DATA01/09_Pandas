# Matrices 

### Exercice Matrice et Recherche

1. **Création du DataFrame :**
    - Utilisez la variable `data` pour créer un DataFrame correspondant à la matrice donnée dans l'énoncé. Respectez les noms des étiquettes (lignes et colonnes).

2. **Suppression des lignes identiques :**
    - Recherchez toutes les lignes identiques dans le DataFrame et supprimez-les en utilisant la méthode `duplicated`.

3. **Comptage des occurrences :**
    - Comptez les occurrences de chaque valeur dans le DataFrame et stockez le résultat dans un dictionnaire.

4. **Somme des nombres pairs :**
    - Faites la somme des nombres pairs de chaque ligne.

```txt
 A   B   C   D   E   F   G   H   I   J
a  13  54  23  23  62  29  53  15  54  67
b  13  54  23  23  62  29  53  15  54  67
c  98  36  34  40  13  92  41  61  94  62
d  33  87  46  44  82  87  11  76  76  21
e  56  16  13  91  64  13  77  44  44  27
f  56  16  13  91  64  13  77  44  44  27
g  15  87  20  50  53  48  39  38  91  32
h  93  48  28  27  50  55  28  38  78  85
i  76  58  26  89  88  71  97  80  42  52
j  76  58  26  89  88  71  97  80  42  52
k  38  98  55  61  75  82  37  64  87  83
l  24  53  16  84  82  13  18  18  82  51
```

- Pour vous aider

```python
 
data = [ 
    [13,  54,  23,  23,  62,  29,  53,  15,  54 , 67],
    [13,  54,  23,  23,  62,  29,  53,  15,  54,  67],
    [98,  36,  34,  40,  13,  92,  41,  61 , 94,  62],
    [33,  87,  46,  44,  82,  87,  11,  76,  76,  21],
    [56,  16 , 13,  91,  64,  13,  77,  44,  44,  27],
    [56,  16 , 13,  91,  64,  13,  77,  44,  44,  27],
    [15 , 87,  20,  50,  53,  48,  39,  38,  91,  32],
    [93,  48,  28,  27,  50 , 55 , 28 , 38  ,78 , 85],
    [76,  58 , 26  ,89 , 88  ,71 , 97 , 80,  42,  52],
    [76,  58 , 26  ,89 , 88  ,71 , 97 , 80,  42,  52],
    [38,  98,  55,  61,  75,  82 , 37,  64,  87,  83],
    [24,  53,  16,  84,  82,  13,  18,  18,  82,  51],
]
```

### Exercice Introduction aux Agrégations

Dans la suite des exercices utiliser la matrice A suivante 

```python
import numpy as np

# Génération de la Matrice A
matrice_a = np.arange(1, 82).reshape(9, -1)
index_labels = list("abcdefghi")
column_labels = list("ABCDEFGHI")
A = pd.DataFrame(matrice_a, index=index_labels, columns=column_labels)
```

1. **Génération de la Matrice A :**
    - Utilisez `np.arange` et la méthode `.reshape` pour générer la matrice A donnée dans l'énoncé.

2. **Calcul des Moyennes par Lignes et Colonnes :**
    - Calculez les moyennes par lignes et colonnes de A en transposant la matrice.

3. **Addition de la Matrice B à A :**
    - Ajoutez la matrice B à la seule colonne possible de la matrice A. Ensuite, faites la somme en lignes et en colonnes en utilisant la transposition.

4. **Calcul des Pourcentages par Ligne et Colonne :**
    - Calculez les pourcentages des valeurs par ligne et par colonne en utilisant la technique de la transposée.

### Exercices Supplémentaires

5. **Produit de Matrices :**
    - Générez deux DataFrames représentant des matrices de dimensions appropriées et calculez leur produit matriciel.

6. **Extraction de Sous-Matrice :**
    - À partir d'une matrice donnée, extrayez une sous-matrice de taille 3x3.

7. **Recherche de Valeur Maximale :**
    - Trouvez la valeur maximale dans chaque ligne et chaque colonne de la matrice.

8. **Filtrage avec Critères :**
    - Filtrez les éléments de la matrice qui sont supérieurs à la moyenne de la matrice.
