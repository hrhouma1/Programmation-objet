# Pratique 6: Les listes en Python

Cette pratique vous permettra d’explorer les fonctionnalités des listes en Python, y compris la création, la manipulation, et les méthodes courantes. Vous pouvez tester les exemples en **ligne de commande avec `python3 -c`** ou en créant un fichier Python.

---

## Préparation

1. **Créer un environnement virtuel** :
   ```bash
   python3 -m venv pratique_env
   ```

2. **Activer l’environnement virtuel** :
   - **Windows** :
     ```cmd
     pratique_env\Scripts\activate
     ```
   - **Linux/macOS** :
     ```bash
     source pratique_env/bin/activate
     ```

3. **Créer un fichier Python** (si nécessaire) :
   - **Windows** :
     ```cmd
     notepad exercice_listes.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_listes.py
     ```

---

## Exercices

### 1. Créer une liste

#### Avec **`python3 -c`** :
```bash
python3 -c "
ma_liste = [42, 'Python', 3.14, False]
print(ma_liste)
"
```

#### Dans le fichier `exercice_listes.py` :
1. Ajoutez ce code :
   ```python
   ma_liste = [42, "Python", 3.14, False]
   print(ma_liste)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_listes.py
   ```

3. **Résultat attendu** :
   ```plaintext
   [42, 'Python', 3.14, False]
   ```

---

### 2. Accéder aux éléments d’une liste

#### Avec **`python3 -c`** :
```bash
python3 -c "
animaux = ['chien', 'chat', 'lapin']
print(animaux[0])  # Premier élément
print(animaux[-1])  # Dernier élément
"
```

#### Dans le fichier `exercice_listes.py` :
1. Ajoutez ce code après le précédent :
   ```python
   animaux = ["chien", "chat", "lapin"]
   print(animaux[0])  # Premier élément
   print(animaux[-1])  # Dernier élément
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_listes.py
   ```

3. **Résultat attendu** :
   ```plaintext
   chien
   lapin
   ```

---

### 3. Modifier une liste

#### Avec **`python3 -c`** :
```bash
python3 -c "
fruits = ['pomme', 'orange']
fruits.append('banane')
fruits.extend(['kiwi', 'mangue'])
print(fruits)
"
```

#### Dans le fichier `exercice_listes.py` :
1. Ajoutez ce code :
   ```python
   fruits = ["pomme", "orange"]
   fruits.append("banane")
   fruits.extend(["kiwi", "mangue"])
   print(fruits)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_listes.py
   ```

3. **Résultat attendu** :
   ```plaintext
   ['pomme', 'orange', 'banane', 'kiwi', 'mangue']
   ```

---

### 4. Concaténation et répétition de listes

#### Avec **`python3 -c`** :
```bash
python3 -c "
liste1 = [1, 2]
liste2 = [3, 4]
resultat = liste1 + liste2
repetition = liste1 * 3
print(resultat)
print(repetition)
"
```

#### Dans le fichier `exercice_listes.py` :
1. Ajoutez ce code :
   ```python
   liste1 = [1, 2]
   liste2 = [3, 4]
   resultat = liste1 + liste2
   repetition = liste1 * 3
   print(resultat)
   print(repetition)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_listes.py
   ```

3. **Résultat attendu** :
   ```plaintext
   [1, 2, 3, 4]
   [1, 2, 1, 2, 1, 2]
   ```

---

### 5. Parcourir une liste

#### Avec **`python3 -c`** :
```bash
python3 -c "
couleurs = ['rouge', 'vert', 'bleu']
for couleur in couleurs:
    print(couleur)
"
```

#### Dans le fichier `exercice_listes.py` :
1. Ajoutez ce code :
   ```python
   couleurs = ["rouge", "vert", "bleu"]
   for couleur in couleurs:
       print(couleur)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_listes.py
   ```

3. **Résultat attendu** :
   ```plaintext
   rouge
   vert
   bleu
   ```

---

### 6. Slicing et inversion

#### Avec **`python3 -c`** :
```bash
python3 -c "
nombres = [0, 1, 2, 3, 4, 5]
print(nombres[1:4])  # Sous-liste
print(nombres[::-1])  # Liste inversée
"
```

#### Dans le fichier `exercice_listes.py` :
1. Ajoutez ce code :
   ```python
   nombres = [0, 1, 2, 3, 4, 5]
   print(nombres[1:4])  # Sous-liste
   print(nombres[::-1])  # Liste inversée
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_listes.py
   ```

3. **Résultat attendu** :
   ```plaintext
   [1, 2, 3]
   [5, 4, 3, 2, 1, 0]
   ```

---

### 7. Méthodes utiles pour les listes

#### Avec **`python3 -c`** :
```bash
python3 -c "
nombres = [3, 1, 4, 1, 5]
print(nombres.count(1))  # Compte les 1
print(nombres.index(4))  # Position de 4
nombres.sort()
print(nombres)  # Trié
nombres.reverse()
print(nombres)  # Ordre inversé
"
```

#### Dans le fichier `exercice_listes.py` :
1. Ajoutez ce code :
   ```python
   nombres = [3, 1, 4, 1, 5]
   print(nombres.count(1))  # Compte les 1
   print(nombres.index(4))  # Position de 4
   nombres.sort()
   print(nombres)  # Trié
   nombres.reverse()
   print(nombres)  # Ordre inversé
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_listes.py
   ```

3. **Résultat attendu** :
   ```plaintext
   2
   2
   [1, 1, 3, 4, 5]
   [5, 4, 3, 1, 1]
   ```

---

## Résumé des commandes

1. **Exécuter une commande Python directement** :
   ```bash
   python3 -c "print([1, 2, 3])"
   ```

2. **Créer un fichier Python** :
   - **Windows** :
     ```cmd
     notepad exercice_listes.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_listes.py
     ```

3. **Exécuter un fichier Python** :
   ```bash
   python3 exercice_listes.py
   ```

4. **Activer/Désactiver un environnement virtuel** :
   - Activer :
     ```bash
     source pratique_env/bin/activate  # Linux/macOS
     pratique_env\Scripts\activate  # Windows
     ```
   - Désactiver :
     ```bash
     deactivate
     ```
