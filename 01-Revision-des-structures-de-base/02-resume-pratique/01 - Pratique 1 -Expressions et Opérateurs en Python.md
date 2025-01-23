# Pratique 1 : Expressions et Opérateurs en Python

## Objectif
- Pratiquer les expressions, opérateurs et types de données Python en écrivant et exécutant du code dans des fichiers distincts.

---

## Note préalable
Le module `venv` est inclus par défaut avec Python 3.3 et versions ultérieures.  
Si vous utilisez une version de Python inférieure ou si le module n'est pas installé, assurez-vous d'avoir activé l'option **"Add Python to PATH"** lors de l'installation de Python.

---

## Préparation
1. Configurez un environnement virtuel et créez deux fichiers Python :
   ```bash
   python -m venv pratique_env
   pratique_env\Scripts\activate  # Active l'environnement virtuel
   notepad exercice2-partie1.py   # Fichier pour les exercices 1 à 3
   notepad exercice2-partie2.py   # Fichier pour les exercices 4 à 6
   ```

2. Exécutez chaque fichier une fois le code ajouté :
   ```bash
   python exercice2-partie1.py
   python exercice2-partie2.py
   ```

---

## Exercices

### Fichier : `exercice2-partie1.py`

#### 1. Expressions simples
Ajoutez ce code dans `exercice2-partie1.py` :
```python
print(3 + 5)  # Addition
print("Python" + " est génial")  # Concaténation
print(len("Programmation"))  # Longueur d'une chaîne
```

#### 2. Opérateurs arithmétiques
Ajoutez ensuite :
```python
print(10 / 3)  # Division
print(10 // 3)  # Division entière
print(2 ** 3)  # Puissance
```

#### 3. Opérateurs de comparaison
Ajoutez enfin :
```python
print(10 > 3)  # Supérieur
print(10 == 10)  # Égalité
print(5 != 2)  # Différent
```

#### Résultat attendu pour `exercice2-partie1.py` :
```
8
Python est génial
13
3.3333333333333335
3
8
True
True
True
```

---

### Fichier : `exercice2-partie2.py`

#### 4. Opérateurs logiques
Ajoutez ce code dans `exercice2-partie2.py` :
```python
print((5 > 3) and (3 < 10))  # AND logique
print((5 > 3) or (3 > 10))  # OR logique
print(not (5 > 3))  # NOT logique
```

#### 5. Opérateurs d'appartenance
Ajoutez ensuite :
```python
print('a' in 'apple')  # Appartenance
print('z' not in 'apple')  # Non-appartenance
```

#### 6. Types de données
Ajoutez enfin :
```python
x = 5
y = 3.14
texte = "Python"

print(type(x))  # Entier
print(type(y))  # Flottant
print(type(texte))  # Chaîne
```

#### Résultat attendu pour `exercice2-partie2.py` :
```
True
True
False
True
True
<class 'int'>
<class 'float'>
<class 'str'>
```

---

## Résumé des étapes

1. **Créer les fichiers :**
   - `exercice2-partie1.py` : Contient les exercices 1 à 3.
   - `exercice2-partie2.py` : Contient les exercices 4 à 6.

2. **Exécuter chaque fichier Python :**
   ```bash
   python exercice2-partie1.py
   python exercice2-partie2.py
   ```
