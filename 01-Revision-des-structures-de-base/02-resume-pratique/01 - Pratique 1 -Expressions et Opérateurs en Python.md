# Pratique 1 : Expressions et Opérateurs en Python

## Objectif
Pratiquer les expressions, opérateurs et types de données Python en écrivant et exécutant du code dans des fichiers distincts.

---

## Préparation
1. Configurez un environnement virtuel avec le nom **pratique1** et créez plusieurs fichiers Python :
   ```bash
   python -m venv pratique1
   pratique1\Scripts\activate  # Active l'environnement virtuel
   notepad exemple1.py   # Fichier pour l'exercice 1
   notepad exemple2.py   # Fichier pour l'exercice 2
   notepad exemple3.py   # Fichier pour l'exercice 3
   notepad exemple4.py   # Fichier pour l'exercice 4
   notepad exemple5.py   # Fichier pour l'exercice 5
   notepad exemple6.py   # Fichier pour l'exercice 6
   ```

2. Exécutez chaque fichier après y avoir ajouté le code :
   ```bash
   python exemple1.py
   python exemple2.py
   python exemple3.py
   python exemple4.py
   python exemple5.py
   python exemple6.py
   ```

---

## Exercices

### Fichier : `exemple1.py`

#### 1. Expressions simples
Ajoutez ce code dans `exemple1.py` :
```python
print(3 + 5)  # Addition
print("Python" + " est génial")  # Concaténation
print(len("Programmation"))  # Longueur d'une chaîne
```

#### Résultat attendu pour `exemple1.py` :
```
8
Python est génial
13
```

---

### Fichier : `exemple2.py`

#### 2. Opérateurs arithmétiques
Ajoutez ce code dans `exemple2.py` :
```python
print(10 / 3)  # Division
print(10 // 3)  # Division entière
print(2 ** 3)  # Puissance
```

#### Résultat attendu pour `exemple2.py` :
```
3.3333333333333335
3
8
```

---

### Fichier : `exemple3.py`

#### 3. Opérateurs de comparaison
Ajoutez ce code dans `exemple3.py` :
```python
print(10 > 3)  # Supérieur
print(10 == 10)  # Égalité
print(5 != 2)  # Différent
```

#### Résultat attendu pour `exemple3.py` :
```
True
True
True
```

---

### Fichier : `exemple4.py`

#### 4. Opérateurs logiques
Ajoutez ce code dans `exemple4.py` :
```python
print((5 > 3) and (3 < 10))  # AND logique
print((5 > 3) or (3 > 10))  # OR logique
print(not (5 > 3))  # NOT logique
```

#### Résultat attendu pour `exemple4.py` :
```
True
True
False
```

---

### Fichier : `exemple5.py`

#### 5. Opérateurs d'appartenance
Ajoutez ce code dans `exemple5.py` :
```python
print('a' in 'apple')  # Appartenance
print('z' not in 'apple')  # Non-appartenance
```

#### Résultat attendu pour `exemple5.py` :
```
True
True
```

---

### Fichier : `exemple6.py`

#### 6. Types de données
Ajoutez ce code dans `exemple6.py` :
```python
x = 5
y = 3.14
texte = "Python"

print(type(x))  # Entier
print(type(y))  # Flottant
print(type(texte))  # Chaîne
```

#### Résultat attendu pour `exemple6.py` :
```
<class 'int'>
<class 'float'>
<class 'str'>
```

---

## Résumé des étapes

1. **Créer les fichiers :**
   - `exemple1.py` : Contient l'exercice 1.
   - `exemple2.py` : Contient l'exercice 2.
   - `exemple3.py` : Contient l'exercice 3.
   - `exemple4.py` : Contient l'exercice 4.
   - `exemple5.py` : Contient l'exercice 5.
   - `exemple6.py` : Contient l'exercice 6.

2. **Exécuter chaque fichier Python :**
   ```bash
   python exemple1.py
   python exemple2.py
   python exemple3.py
   python exemple4.py
   python exemple5.py
   python exemple6.py
   ```
