# Cours : Raccourcis avec NumPy — `loadtxt` et `savetxt`

## Objectifs :
- Comprendre comment charger et sauvegarder efficacement des fichiers texte avec NumPy.
- Maîtriser les options essentielles des fonctions `np.loadtxt()` et `np.savetxt()`.

---

## Partie 1 : La fonction `np.loadtxt()`

### Définition :
```python
numpy.loadtxt(fname, dtype=float, delimiter=None, skiprows=0, usecols=None)
```

### Description :
Permet de **charger rapidement des données numériques** depuis un fichier texte ou `.csv`, sous forme de tableau NumPy.

---

### Exemple 1 : Chargement simple

Contenu du fichier `donnees.csv` :
```
1.0,2.0,3.0
4.0,5.0,6.0
7.0,8.0,9.0
```

```python
import numpy as np

donnees = np.loadtxt("donnees.csv", delimiter=",")
print(donnees)
```

### Résultat :
```
[[1. 2. 3.]
 [4. 5. 6.]
 [7. 8. 9.]]
```

---

### Exemple 2 : Ignorer une ligne d'en-tête

Contenu du fichier `data.txt` :
```
# x y z
10 20 30
40 50 60
```

```python
data = np.loadtxt("data.txt", skiprows=1)
```

---

### Paramètres utiles :
| Paramètre   | Description |
|-------------|-------------|
| `delimiter` | Séparateur : `","`, `" "`, `"\t"`, etc. |
| `skiprows`  | Ignore les premières lignes (utile pour les en-têtes) |
| `usecols`   | Extrait uniquement certaines colonnes (ex: `usecols=(0,2)`) |
| `dtype`     | Type des données (`float`, `int`, etc.) |

---

## Partie 2 : La fonction `np.savetxt()`

### Définition :
```python
numpy.savetxt(fname, X, fmt='%.18e', delimiter=' ', newline='\n')
```

### Description :
Permet de **sauvegarder un tableau NumPy** dans un fichier texte sous forme structurée.

---

### Exemple 1 : Sauvegarde de données

```python
import numpy as np

matrice = np.array([[1.5, 2.5, 3.5], [4.1, 5.2, 6.3]])
np.savetxt("sortie.txt", matrice, delimiter=",")
```

**Contenu de `sortie.txt` :**
```
1.5,2.5,3.5
4.1,5.2,6.3
```

---

### Exemple 2 : Formater la sortie

```python
np.savetxt("arrondi.txt", matrice, delimiter=",", fmt="%.2f")
```

**Résultat :**
```
1.50,2.50,3.50
4.10,5.20,6.30
```

---

### Paramètres utiles :
| Paramètre | Description |
|-----------|-------------|
| `delimiter` | Caractère de séparation |
| `fmt`       | Format de sortie (`%.2f` pour 2 décimales) |
| `newline`   | Caractère de fin de ligne (par défaut : `\n`) |

---

## Bonus : Enchaînement lecture → traitement → écriture

```python
# Lecture d'un fichier
donnees = np.loadtxt("donnees.csv", delimiter=",")

# Transformation (exemple : doubler les valeurs)
donnees *= 2

# Sauvegarde des résultats
np.savetxt("resultat.csv", donnees, delimiter=",", fmt="%.1f")
```

---

## Erreurs fréquentes à éviter

| Erreur | Cause | Solution |
|--------|-------|----------|
| `ValueError: could not convert string to float` | Fichier contient du texte non numérique | Utiliser `skiprows` ou vérifier le contenu |
| `FileNotFoundError` | Chemin incorrect | Vérifier le chemin relatif/absolu du fichier |
| Mauvais affichage | Format non adapté | Utiliser `fmt="%.2f"` ou `delimiter=","` |

