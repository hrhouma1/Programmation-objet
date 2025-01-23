# Pratique 3: Les structures itératives en Python

Cette pratique vous permettra d'appliquer les concepts des boucles `while` et `for` à travers des exercices concrets. Vous pourrez tester chaque exemple directement via la **ligne de commande avec `python3 -c`** ou en **écrivant du code dans un fichier Python**.

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

3. **Créer un fichier Python** (si nécessaire) :
   - **Windows** :
     ```cmd
     notepad exercice_boucles.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_boucles.py
     ```

---

## Exercices

### 1. La boucle `while`

#### Avec **`python3 -c`** :
```bash
python3 -c "
compteur = 1
while compteur <= 5:
    print(compteur)
    compteur += 1
"
```

#### Dans le fichier `exercice_boucles.py` :
1. Ajoutez ce code :
   ```python
   compteur = 1
   while compteur <= 5:
       print(compteur)
       compteur += 1
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_boucles.py
   ```

3. **Résultat attendu** :
   ```plaintext
   1
   2
   3
   4
   5
   ```

---

### 2. Demander une entrée utilisateur avec `while`

#### Avec **`python3 -c`** :
```bash
python3 -c "
nombre = 0
while nombre <= 0:
    nombre = int(input('Veuillez entrer un nombre supérieur à zéro : '))
print(f'Vous avez entré {nombre}. Merci !')
"
```

#### Dans le fichier `exercice_boucles.py` :
1. Ajoutez ce code après le précédent :
   ```python
   nombre = 0
   while nombre <= 0:
       nombre = int(input("Veuillez entrer un nombre supérieur à zéro : "))
   print(f"Vous avez entré {nombre}. Merci !")
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_boucles.py
   ```

3. **Exemple de session** :
   ```plaintext
   Veuillez entrer un nombre supérieur à zéro : -3
   Veuillez entrer un nombre supérieur à zéro : 5
   Vous avez entré 5. Merci !
   ```

---

### 3. La boucle `for`

#### Avec **`python3 -c`** :
```bash
python3 -c "
animaux = ['chat', 'chien', 'oiseau']
for animal in animaux:
    print(animal)
"
```

#### Dans le fichier `exercice_boucles.py` :
1. Ajoutez ce code :
   ```python
   animaux = ["chat", "chien", "oiseau"]
   for animal in animaux:
       print(animal)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_boucles.py
   ```

3. **Résultat attendu** :
   ```plaintext
   chat
   chien
   oiseau
   ```

---

### 4. Utilisation de `range`

#### Avec **`python3 -c`** :
```bash
python3 -c "
for nombre in range(1, 6):
    print(nombre)
"
```

#### Dans le fichier `exercice_boucles.py` :
1. Ajoutez ce code :
   ```python
   for nombre in range(1, 6):
       print(nombre)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_boucles.py
   ```

3. **Résultat attendu** :
   ```plaintext
   1
   2
   3
   4
   5
   ```

---

### 5. Boucles imbriquées

#### Avec **`python3 -c`** :
```bash
python3 -c "
taille = 4
for i in range(taille):
    for j in range(taille):
        print('#', end='')
    print()
"
```

#### Dans le fichier `exercice_boucles.py` :
1. Ajoutez ce code :
   ```python
   taille = 4
   for i in range(taille):
       for j in range(taille):
           print("#", end="")
       print()
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_boucles.py
   ```

3. **Résultat attendu** :
   ```plaintext
   ####
   ####
   ####
   ####
   ```

---

### 6. Exercice global : Calculer une table de multiplication

1. **Objectif** :
   Afficher une table de multiplication pour les nombres de 1 à 5.

#### Avec **`python3 -c`** :
```bash
python3 -c "
for i in range(1, 6):
    for j in range(1, 6):
        print(f'{i * j:2}', end=' ')
    print()
"
```

#### Dans le fichier `exercice_boucles.py` :
1. Ajoutez ce code :
   ```python
   for i in range(1, 6):
       for j in range(1, 6):
           print(f"{i * j:2}", end=" ")
       print()
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_boucles.py
   ```

3. **Résultat attendu** :
   ```plaintext
    1  2  3  4  5
    2  4  6  8 10
    3  6  9 12 15
    4  8 12 16 20
    5 10 15 20 25
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
     notepad exercice_boucles.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_boucles.py
     ```

3. **Exécuter un fichier Python** :
   ```bash
   python3 exercice_boucles.py
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

## Accessibilité pour tous

- Les explications sont conçues pour guider chaque étape clairement.
- Tous les résultats attendus sont détaillés pour validation.
- Les commandes sont adaptées pour la saisie rapide et la vérification via un terminal ou un fichier.

Avec cette pratique, vous développerez une compréhension solide des **structures itératives** en Python.
