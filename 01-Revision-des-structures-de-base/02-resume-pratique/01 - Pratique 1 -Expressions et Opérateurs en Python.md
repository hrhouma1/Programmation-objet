# Pratique 1 : Expressions et Opérateurs en Python

## Objectif
Pratiquer les expressions, opérateurs et types de données Python en écrivant et exécutant du code dans des fichiers distincts ou directement depuis la ligne de commande.

---

## Note préalable
Le module `venv` est inclus par défaut dans Python 3.3 et versions ultérieures.  
- **Si `venv` n'est pas disponible**, installez-le avec :
  ```bash
  pip install venv
  ```

- **Pour plusieurs versions de Python installées** : Vous pouvez exécuter une version spécifique en utilisant des commandes comme `python3.11`, `python3.12`, ou `python3.7`.

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

---

### Fichier : `exemple2.py`

#### 2. Opérateurs arithmétiques
Ajoutez ce code dans `exemple2.py` :
```python
print(10 / 3)  # Division
print(10 // 3)  # Division entière
print(2 ** 3)  # Puissance
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

---

### Fichier : `exemple4.py`

#### 4. Opérateurs logiques
Ajoutez ce code dans `exemple4.py` :
```python
print((5 > 3) and (3 < 10))  # AND logique
print((5 > 3) or (3 > 10))  # OR logique
print(not (5 > 3))  # NOT logique
```

---

### Fichier : `exemple5.py`

#### 5. Opérateurs d'appartenance
Ajoutez ce code dans `exemple5.py` :
```python
print('a' in 'apple')  # Appartenance
print('z' not in 'apple')  # Non-appartenance
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

---

## Annexe : Exécution rapide avec `python -c`

### Méthode
Vous pouvez exécuter des expressions simples directement depuis la ligne de commande avec `python -c` :
- Pour des versions spécifiques : `python3.11 -c`, `python3.12 -c`, etc.

### Exemples

#### Exercice 1 : Expressions simples
```bash
python -c "print(3 + 5)"  # Addition
python -c "print('Python' + ' est génial')"  # Concaténation
python -c "print(len('Programmation'))"  # Longueur d'une chaîne
```

#### Exercice 2 : Opérateurs arithmétiques
```bash
python -c "print(10 / 3)"  # Division
python -c "print(10 // 3)"  # Division entière
python -c "print(2 ** 3)"  # Puissance
```

#### Exercice 3 : Opérateurs de comparaison
```bash
python -c "print(10 > 3)"  # Supérieur
python -c "print(10 == 10)"  # Égalité
python -c "print(5 != 2)"  # Différent
```

#### Exercice 4 : Opérateurs logiques
```bash
python -c "print((5 > 3) and (3 < 10))"  # AND logique
python -c "print((5 > 3) or (3 > 10))"  # OR logique
python -c "print(not (5 > 3))"  # NOT logique
```

#### Exercice 5 : Opérateurs d'appartenance
```bash
python -c "print('a' in 'apple')"  # Appartenance
python -c "print('z' not in 'apple')"  # Non-appartenance
```

#### Exercice 6 : Types de données
```bash
python -c "x = 5; y = 3.14; texte = 'Python'; print(type(x)); print(type(y)); print(type(texte))"
```

---

### Avantages de `python -c`
1. **Rapide** : Permet de tester une seule ligne sans créer de fichier.
2. **Flexible** : Exécutez facilement avec différentes versions de Python.

### Résumé
- **Pour des tests rapides**, utilisez `python -c`.
- **Pour des scripts plus longs ou réutilisables**, créez et exécutez des fichiers Python comme dans les sections principales.
