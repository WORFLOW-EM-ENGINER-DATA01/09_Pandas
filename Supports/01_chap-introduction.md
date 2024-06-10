# Pandas

## Chapitre 1 : Introduction à Pandas

### 1.1 Qu'est-ce que Pandas ?

Pandas est une bibliothèque open-source pour le langage de programmation Python, offrant des structures de données et des outils d'analyse de données hautes performances et faciles à utiliser. Pandas permet de manipuler des données de manière efficace, notamment à travers des structures appelées DataFrame et Series.

### 1.2 Installation de Pandas

Si vous n'avez pas encore Pandas installé, vous pouvez l'installer en utilisant pip :

```bash
pip install pandas
```

### 1.3 Structures de données principales

#### 1.3.1 Series

Une `Series` est un tableau unidimensionnel semblable à un tableau numpy, mais avec des étiquettes d'axe. Une `Series` peut contenir des données de tout type (entiers, flottants, chaînes, etc.).

Exemple de création d'une `Series` :

```python
import pandas as pd

data = [1, 2, 3, 4, 5]
series = pd.Series(data)
print(series)
```

#### 1.3.2 DataFrame

Un `DataFrame` est une structure de données bidimensionnelle avec des colonnes d'étiquettes potentiellement de différents types. C'est l'équivalent d'une feuille de calcul ou d'une table SQL.

Exemple de création d'un `DataFrame` :

```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Los Angeles', 'Chicago']
}

df = pd.DataFrame(data)
print(df)
```

### 1.4 Lecture et écriture de fichiers

#### 1.4.1 Lire un fichier CSV

```python
df = pd.read_csv('data.csv')
print(df)
```

#### 1.4.2 Écrire un DataFrame dans un fichier CSV

```python
df.to_csv('output.csv', index=False)
```

#### 1.4.3 Lire un fichier Excel

```python
df = pd.read_excel('data.xlsx')
print(df)
```

#### 1.4.4 Écrire un DataFrame dans un fichier Excel

```python
df.to_excel('output.xlsx', index=False)
```

### 1.5 Manipulation de données

#### 1.5.1 Sélection et filtrage

Sélection de colonnes :

```python
print(df['Name'])
```

Filtrage des lignes :

```python
filtered_df = df[df['Age'] > 30]
print(filtered_df)
```

#### 1.5.2 Ajout et suppression de colonnes

Ajout d'une colonne :

```python
df['Salary'] = [50000, 60000, 70000]
print(df)
```

Suppression d'une colonne :

```python
df.drop('Salary', axis=1, inplace=True)
print(df)
```

### 1.6 Statistiques descriptives

Pandas offre des méthodes pour obtenir des statistiques descriptives rapidement :

```python
print(df.describe())
```

---

## Chapitre 2 : Exercices création Df

### Exercice 1 : Création d'un DataFrame

Créez un DataFrame avec les données suivantes et affichez-le.

| Nom       | Âge | Ville         |
|-----------|-----|---------------|
| Alice     | 24  | Paris         |
| Bob       | 30  | Lyon          |
| Charlie   | 22  | Marseille     |
| David     | 35  | Bordeaux      |

## Exercice 2 : Lecture d'un fichier CSV

Lisez un fichier CSV nommé `employees.csv` et affichez les 5 premières lignes.

### Exercice 3 : Filtrage des données

À partir du DataFrame de l'exercice 1, filtrez les lignes où l'âge est supérieur à 25 ans.


### Exercice 4 : Ajout d'une colonne

Ajoutez une colonne `Salaire` au DataFrame de l'exercice 1 avec les valeurs suivantes : [50000, 60000, 55000, 70000].


### Exercice 5 : Statistiques descriptives

Affichez les statistiques descriptives du DataFrame de l'exercice 1.

### Exercice 6 

Augmentez les salaires de 10% pour l'ensemble des Persons