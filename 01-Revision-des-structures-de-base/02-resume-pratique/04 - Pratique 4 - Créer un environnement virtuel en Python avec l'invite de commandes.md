# Pratique : Les chaînes de caractères en Python

Cette pratique vous permettra de travailler sur la manipulation et la transformation des chaînes en Python. Vous pourrez tester chaque exercice en utilisant la **ligne de commande avec `python3 -c`** ou en **écrivant un fichier Python**.

---

## Préparation

1. **Créer un environnement virtuel** :
   ```bash
   python3 -m venv pratique_env
   ```

2. **Activer l'environnement virtuel** :
   - **Windows** :
     ```cmd
     pratique_env\Scripts\activate
     ```
   - **Linux/macOS** :
     ```bash
     source pratique_env/bin/activate
     ```

3. **Créer un fichier Python** :
   - **Windows** :
     ```cmd
     notepad exercice_chaine.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_chaine.py
     ```

---

## Exercices

### 1. Concaténation de chaînes

#### Avec **`python3 -c`** :
```bash
python3 -c "
prenom = 'Alice'
nom = 'Martin'
nom_complet = prenom + ' ' + nom
print(nom_complet)
"
```

#### Dans le fichier `exercice_chaine.py` :
1. Ajoutez ce code :
   ```python
   prenom = "Alice"
   nom = "Martin"
   nom_complet = prenom + " " + nom
   print(nom_complet)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_chaine.py
   ```

3. **Résultat attendu** :
   ```plaintext
   Alice Martin
   ```

---

### 2. Interpolation de chaînes

#### Avec **`python3 -c`** :
```bash
python3 -c "
ville = 'Paris'
message = f'Bienvenue à {ville} !'
print(message)
"
```

#### Dans le fichier `exercice_chaine.py` :
1. Ajoutez ce code :
   ```python
   ville = "Paris"
   message = f"Bienvenue à {ville} !"
   print(message)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_chaine.py
   ```

3. **Résultat attendu** :
   ```plaintext
   Bienvenue à Paris !
   ```

---

### 3. Indexation et extraction de sous-chaînes

#### Avec **`python3 -c`** :
```bash
python3 -c "
texte = 'Python'
print(texte[0])  # Premier caractère
print(texte[-1])  # Dernier caractère
print(texte[0:3])  # Sous-chaîne
"
```

#### Dans le fichier `exercice_chaine.py` :
1. Ajoutez ce code :
   ```python
   texte = "Python"
   print(texte[0])  # Premier caractère
   print(texte[-1])  # Dernier caractère
   print(texte[0:3])  # Sous-chaîne
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_chaine.py
   ```

3. **Résultat attendu** :
   ```plaintext
   P
   n
   Pyt
   ```

---

### 4. Méthodes de transformation de chaînes

#### Avec **`python3 -c`** :
```bash
python3 -c "
texte = ' Bonjour '
print(texte.upper())  # Majuscules
print(texte.lower())  # Minuscules
print(texte.strip())  # Suppression d'espaces
"
```

#### Dans le fichier `exercice_chaine.py` :
1. Ajoutez ce code :
   ```python
   texte = " Bonjour "
   print(texte.upper())  # Majuscules
   print(texte.lower())  # Minuscules
   print(texte.strip())  # Suppression d'espaces
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_chaine.py
   ```

3. **Résultat attendu** :
   ```plaintext
   BONJOUR
   bonjour
   Bonjour
   ```

---

### 5. Recherche et remplacement

#### Avec **`python3 -c`** :
```bash
python3 -c "
texte = 'Apprendre Python est amusant.'
print(texte.find('Python'))  # Trouver 'Python'
print(texte.replace('Python', 'la programmation'))  # Remplacer
"
```

#### Dans le fichier `exercice_chaine.py` :
1. Ajoutez ce code :
   ```python
   texte = "Apprendre Python est amusant."
   print(texte.find("Python"))  # Trouver 'Python'
   print(texte.replace("Python", "la programmation"))  # Remplacer
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_chaine.py
   ```

3. **Résultat attendu** :
   ```plaintext
   9
   Apprendre la programmation est amusant.
   ```

---

### 6. Découpage et assemblage

#### Avec **`python3 -c`** :
```bash
python3 -c "
phrase = 'Python est génial'
mots = phrase.split(' ')  # Découper
print(mots)
nouvelle_phrase = ' '.join(mots)  # Assembler
print(nouvelle_phrase)
"
```

#### Dans le fichier `exercice_chaine.py` :
1. Ajoutez ce code :
   ```python
   phrase = "Python est génial"
   mots = phrase.split(" ")  # Découper
   print(mots)
   nouvelle_phrase = " ".join(mots)  # Assembler
   print(nouvelle_phrase)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_chaine.py
   ```

3. **Résultat attendu** :
   ```plaintext
   ['Python', 'est', 'génial']
   Python est génial
   ```

---

### 7. Exercice global : Transformation et analyse

1. **Objectif** :
   Écrire un programme qui transforme une phrase en majuscules, compte les mots et remplace un mot spécifique.

#### Avec **`python3 -c`** :
```bash
python3 -c "
phrase = 'La programmation en Python est passionnante.'
print(phrase.upper())  # Majuscules
print(len(phrase.split()))  # Compte les mots
print(phrase.replace('Python', 'JavaScript'))  # Remplacer Python par JavaScript
"
```

#### Dans le fichier `exercice_chaine.py` :
1. Ajoutez ce code :
   ```python
   phrase = "La programmation en Python est passionnante."
   print(phrase.upper())  # Majuscules
   print(len(phrase.split()))  # Compte les mots
   print(phrase.replace("Python", "JavaScript"))  # Remplacer Python par JavaScript
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_chaine.py
   ```

3. **Résultat attendu** :
   ```plaintext
   LA PROGRAMMATION EN PYTHON EST PASSIONNANTE.
   6
   La programmation en JavaScript est passionnante.
   ```

---

## Résumé des commandes

1. **Exécuter une commande Python directement** :
   ```bash
   python3 -c "print('Bonjour !')"
   ```

2. **Créer un fichier Python** :
   - **Windows** :
     ```cmd
     notepad exercice_chaine.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_chaine.py
     ```

3. **Exécuter un fichier Python** :
   ```bash
   python3 exercice_chaine.py
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

---

## Accessibilité

- Les instructions sont claires et chaque résultat attendu est décrit.
- Les commandes offrent une méthode alternative (`python3 -c`) pour tester rapidement sans créer de fichiers.
- Les exercices progressent en difficulté pour renforcer la compréhension.

Cette pratique vous permettra de manipuler efficacement les chaînes de caractères en Python.
