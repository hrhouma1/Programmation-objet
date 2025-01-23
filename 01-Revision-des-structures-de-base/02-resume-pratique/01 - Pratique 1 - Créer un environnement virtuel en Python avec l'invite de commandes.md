# Pratique 1 : Expressions et Opérateurs en Python

## Objectif

Vous allez pratiquer les concepts des expressions, opérateurs, et types de données Python en testant directement via :
1. La commande **`python3 -c`** pour exécuter du code en ligne.
2. L’écriture et l’exécution d’un fichier Python (`exercice2.py`).

---

## Préparation

1. **Créer un environnement virtuel** :
   ```bash
   python3 -m venv pratique_env
   ```
2. **Activer l’environnement virtuel** :
   - Sous Windows :
     ```bash
     pratique_env\Scripts\activate
     ```
   - Sous Linux/macOS :
     ```bash
     source pratique_env/bin/activate
     ```

3. **Créer un fichier Python (facultatif)** :
   - Sous Windows :
     ```cmd
     notepad exercice2.py
     ```
   - Sous Linux/macOS :
     ```bash
     nano exercice2.py
     ```

---

## Exercices

### 1. Expressions simples

#### Avec **`python3 -c`** :
```bash
python3 -c "print(3 + 5)"  # Addition
python3 -c "print('Python' + ' est génial')"  # Concaténation
python3 -c "print(len('Programmation'))"  # Longueur
```

#### Dans le fichier `exercice2.py` :
1. Ajoutez ce code :
   ```python
   print(3 + 5)  # Addition
   print("Python" + " est génial")  # Concaténation
   print(len("Programmation"))  # Longueur d'une chaîne
   ```
2. **Exécutez avec** :
   ```bash
   python3 exercice2.py
   ```

3. **Résultat attendu** :
   ```plaintext
   8
   Python est génial
   13
   ```

---

### 2. Opérateurs arithmétiques

#### Avec **`python3 -c`** :
```bash
python3 -c "print(10 / 3)"  # Division
python3 -c "print(10 // 3)"  # Division entière
python3 -c "print(2 ** 3)"  # Puissance
```

#### Dans le fichier `exercice2.py` :
1. Ajoutez ce code après le précédent :
   ```python
   print(10 / 3)  # Division
   print(10 // 3)  # Division entière
   print(2 ** 3)  # Puissance
   ```
2. **Exécutez avec** :
   ```bash
   python3 exercice2.py
   ```

3. **Résultat attendu** :
   ```plaintext
   3.3333333333333335
   3
   8
   ```

---

### 3. Opérateurs de comparaison

#### Avec **`python3 -c`** :
```bash
python3 -c "print(10 > 3)"
python3 -c "print(10 == 10)"
python3 -c "print(5 != 2)"
```

#### Dans le fichier `exercice2.py` :
1. Ajoutez ce code :
   ```python
   print(10 > 3)  # Supérieur
   print(10 == 10)  # Égalité
   print(5 != 2)  # Différent
   ```
2. **Exécutez avec** :
   ```bash
   python3 exercice2.py
   ```

3. **Résultat attendu** :
   ```plaintext
   True
   True
   True
   ```

---

### 4. Opérateurs logiques

#### Avec **`python3 -c`** :
```bash
python3 -c "print((5 > 3) and (3 < 10))"
python3 -c "print((5 > 3) or (3 > 10))"
python3 -c "print(not (5 > 3))"
```

#### Dans le fichier `exercice2.py` :
1. Ajoutez ce code :
   ```python
   print((5 > 3) and (3 < 10))  # AND logique
   print((5 > 3) or (3 > 10))  # OR logique
   print(not (5 > 3))  # NOT logique
   ```
2. **Exécutez avec** :
   ```bash
   python3 exercice2.py
   ```

3. **Résultat attendu** :
   ```plaintext
   True
   True
   False
   ```

---

### 5. Opérateurs d'appartenance

#### Avec **`python3 -c`** :
```bash
python3 -c "print('a' in 'apple')"  # Appartenance
python3 -c "print('z' not in 'apple')"  # Non-appartenance
```

#### Dans le fichier `exercice2.py` :
1. Ajoutez ce code :
   ```python
   print('a' in 'apple')  # Appartenance
   print('z' not in 'apple')  # Non-appartenance
   ```
2. **Exécutez avec** :
   ```bash
   python3 exercice2.py
   ```

3. **Résultat attendu** :
   ```plaintext
   True
   True
   ```

---

### 6. Types de données

#### Avec **`python3 -c`** :
```bash
python3 -c "x = 5; print(type(x))"  # Type entier
python3 -c "y = 3.14; print(type(y))"  # Type flottant
python3 -c "texte = 'Python'; print(type(texte))"  # Type chaîne
```

#### Dans le fichier `exercice2.py` :
1. Ajoutez ce code :
   ```python
   x = 5
   y = 3.14
   texte = "Python"

   print(type(x))  # Entier
   print(type(y))  # Flottant
   print(type(texte))  # Chaîne
   ```
2. **Exécutez avec** :
   ```bash
   python3 exercice2.py
   ```

3. **Résultat attendu** :
   ```plaintext
   <class 'int'>
   <class 'float'>
   <class 'str'>
   ```

---

## Résumé des deux méthodes

### 1. Exécuter directement avec `python3 -c` :
- Permet de tester rapidement une seule ligne de code :
  ```bash
  python3 -c "print(3 + 5)"
  ```

### 2. Écrire dans un fichier Python et l'exécuter :
1. **Créer le fichier** :
   - Windows :
     ```cmd
     notepad exercice2.py
     ```
   - Linux/macOS :
     ```bash
     nano exercice2.py
     ```

2. **Ajouter votre code dans le fichier.**
3. **Exécuter le fichier** :
   ```bash
   python3 exercice2.py
   ```


