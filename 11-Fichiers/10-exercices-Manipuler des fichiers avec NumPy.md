# Exercices : Manipuler des fichiers avec NumPy (`loadtxt`, `savetxt`)

## 📁 Fichier 1 : `donnees1.csv`
```
1.5,2.0,3.5
4.0,5.5,6.0
7.0,8.5,9.5
```

## 📁 Fichier 2 : `donnees2.txt`
```
# x y z
10 20 30
40 50 60
70 80 90
```

---

## Exercice 1 : Lire un fichier CSV

**Objectif** : Charger les données numériques du fichier `donnees1.csv` et les afficher sous forme de tableau NumPy.

### Instructions :
1. Utilisez `np.loadtxt()` pour charger le fichier
2. Spécifiez le bon délimiteur
3. Affichez la matrice résultante

---

## Exercice 2 : Lire un fichier texte avec en-tête

**Objectif** : Charger `donnees2.txt` tout en ignorant la première ligne (commentaire).

### Instructions :
1. Ignorez la première ligne avec `skiprows`
2. Chargez les données dans une matrice
3. Affichez la moyenne de chaque colonne

---

## Exercice 3 : Extraire certaines colonnes

**Objectif** : Ne charger que les colonnes x et z du fichier `donnees2.txt`.

### Instructions :
1. Utilisez `usecols=(0,2)` pour lire uniquement les colonnes 0 et 2
2. Affichez le tableau résultant

---

## Exercice 4 : Modifier et sauvegarder un fichier

**Objectif** : Lire les données du fichier `donnees1.csv`, les multiplier par 10, et les sauvegarder dans un fichier `resultat.csv`.

### Instructions :
1. Chargez les données
2. Multipliez-les par 10
3. Sauvegardez avec `np.savetxt()`, format avec 1 décimale

---

## Exercice 5 : Créer et sauvegarder un tableau manuellement

**Objectif** : Créer un tableau 2D NumPy de votre choix, et le sauvegarder dans un fichier `export.txt` avec un format lisible.

### Instructions :
1. Créez un tableau avec `np.array()`
2. Sauvegardez avec `np.savetxt()` en utilisant `delimiter=','` et `fmt="%.2f"`

---

# ✅ Corrections

---

## Correction 1 :

```python
import numpy as np

data1 = np.loadtxt("donnees1.csv", delimiter=",")
print(data1)
```

---

## Correction 2 :

```python
data2 = np.loadtxt("donnees2.txt", skiprows=1)
print(data2)

# Moyenne par colonne
print("Moyennes :", np.mean(data2, axis=0))
```

---

## Correction 3 :

```python
colonnes = np.loadtxt("donnees2.txt", skiprows=1, usecols=(0,2))
print(colonnes)
```

---

## Correction 4 :

```python
data = np.loadtxt("donnees1.csv", delimiter=",")
data = data * 10
np.savetxt("resultat.csv", data, delimiter=",", fmt="%.1f")
```

---

## Correction 5 :

```python
tab = np.array([[1.23, 4.56, 7.89], [9.87, 6.54, 3.21]])
np.savetxt("export.txt", tab, delimiter=",", fmt="%.2f")
```

