# Pratique 5 : Les fonctions en Python

Cette pratique vous permettra de manipuler les fonctions en Python, depuis leur définition jusqu’à des usages plus avancés, comme les paramètres variables ou les appels imbriqués. Vous pourrez tester les exemples en utilisant **`python3 -c`** pour des tests rapides ou en créant des fichiers Python.

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
     notepad exercice_fonctions.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_fonctions.py
     ```

---

## Exercices

### 1. Définir une fonction simple

#### Avec **`python3 -c`** :
```bash
python3 -c "
def saluer():
    print('Bonjour !')

saluer()
"
```

#### Dans le fichier `exercice_fonctions.py` :
1. Ajoutez ce code :
   ```python
   def saluer():
       print("Bonjour !")

   saluer()
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_fonctions.py
   ```

3. **Résultat attendu** :
   ```plaintext
   Bonjour !
   ```

---

### 2. Fonction avec paramètres et retour

#### Avec **`python3 -c`** :
```bash
python3 -c "
def additionner(a, b):
    return a + b

print(additionner(5, 7))
"
```

#### Dans le fichier `exercice_fonctions.py` :
1. Ajoutez ce code après le précédent :
   ```python
   def additionner(a, b):
       return a + b

   print(additionner(5, 7))  # Affiche 12
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_fonctions.py
   ```

3. **Résultat attendu** :
   ```plaintext
   12
   ```

---

### 3. Valeurs par défaut pour les paramètres

#### Avec **`python3 -c`** :
```bash
python3 -c "
def saluer(nom='ami'):
    print(f'Bonjour, {nom} !')

saluer()
saluer('Alice')
"
```

#### Dans le fichier `exercice_fonctions.py` :
1. Ajoutez ce code :
   ```python
   def saluer(nom="ami"):
       print(f"Bonjour, {nom} !")

   saluer()  # Affiche "Bonjour, ami !"
   saluer("Alice")  # Affiche "Bonjour, Alice !"
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_fonctions.py
   ```

3. **Résultat attendu** :
   ```plaintext
   Bonjour, ami !
   Bonjour, Alice !
   ```

---

### 4. Retourner plusieurs valeurs

#### Avec **`python3 -c`** :
```bash
python3 -c "
def calculer(valeur):
    carre = valeur ** 2
    cube = valeur ** 3
    return carre, cube

carre, cube = calculer(3)
print(f'Carré : {carre}, Cube : {cube}')
"
```

#### Dans le fichier `exercice_fonctions.py` :
1. Ajoutez ce code :
   ```python
   def calculer(valeur):
       carre = valeur ** 2
       cube = valeur ** 3
       return carre, cube

   carre, cube = calculer(3)
   print(f"Carré : {carre}, Cube : {cube}")  # Affiche "Carré : 9, Cube : 27"
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_fonctions.py
   ```

3. **Résultat attendu** :
   ```plaintext
   Carré : 9, Cube : 27
   ```

---

### 5. Arguments variables avec `*args`

#### Avec **`python3 -c`** :
```bash
python3 -c "
def additionner_tout(*nombres):
    return sum(nombres)

print(additionner_tout(1, 2, 3))
print(additionner_tout(5, 10))
"
```

#### Dans le fichier `exercice_fonctions.py` :
1. Ajoutez ce code :
   ```python
   def additionner_tout(*nombres):
       return sum(nombres)

   print(additionner_tout(1, 2, 3))  # Affiche 6
   print(additionner_tout(5, 10))  # Affiche 15
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_fonctions.py
   ```

3. **Résultat attendu** :
   ```plaintext
   6
   15
   ```

---

### 6. Appeler une fonction depuis une autre

#### Avec **`python3 -c`** :
```bash
python3 -c "
def chauffer_eau(temperature):
    return f'Eau chauffée à {temperature}°C'

def faire_du_the():
    eau = chauffer_eau(100)
    print(f'Préparer le thé avec {eau}.')

faire_du_the()
"
```

#### Dans le fichier `exercice_fonctions.py` :
1. Ajoutez ce code :
   ```python
   def chauffer_eau(temperature):
       return f"Eau chauffée à {temperature}°C"

   def faire_du_the():
       eau = chauffer_eau(100)
       print(f"Préparer le thé avec {eau}.")

   faire_du_the()
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_fonctions.py
   ```

3. **Résultat attendu** :
   ```plaintext
   Préparer le thé avec Eau chauffée à 100°C.
   ```

---

### 7. Exercice global : Gérer des informations dynamiques

#### Objectif :
Créer une fonction qui affiche des informations dynamiques avec des arguments nommés.

#### Avec **`python3 -c`** :
```bash
python3 -c "
def afficher_infos(**infos):
    for cle, valeur in infos.items():
        print(f'{cle} : {valeur}')

afficher_infos(nom='Marie', age=28, ville='Paris')
"
```

#### Dans le fichier `exercice_fonctions.py` :
1. Ajoutez ce code :
   ```python
   def afficher_infos(**infos):
       for cle, valeur in infos.items():
           print(f"{cle} : {valeur}")

   afficher_infos(nom="Marie", age=28, ville="Paris")
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_fonctions.py
   ```

3. **Résultat attendu** :
   ```plaintext
   nom : Marie
   age : 28
   ville : Paris
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
     notepad exercice_fonctions.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_fonctions.py
     ```

3. **Exécuter un fichier Python** :
   ```bash
   python3 exercice_fonctions.py
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
