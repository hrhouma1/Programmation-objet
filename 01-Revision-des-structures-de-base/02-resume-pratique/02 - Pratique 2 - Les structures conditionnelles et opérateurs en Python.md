# Pratique : Les structures conditionnelles et opérateurs en Python

## Objectif
1. Expérimenter les opérateurs logiques et de comparaison.
2. Appliquer les structures conditionnelles pour résoudre des problèmes simples.
3. Maîtriser les deux méthodes d'exécution : **directe** et via **fichier Python**.
4. Pratiquer les **opérateurs**, les **comparateurs**, et les **structures conditionnelles**. Ceci inclut deux méthodes d'exécution : **ligne de commande avec `python3 -c`** et **via un fichier Python**.

---

## Préparation

1. **Créer un environnement virtuel** :
   ```bash
   python3 -m venv pratique_env
   ```

2. **Activer l'environnement** :
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
     notepad exercice_condition.py
     ```
   - **Linux/macOS** :
     ```bash
     nano exercice_condition.py
     ```

---

## Exercices

### 1. Opérateurs logiques

#### Avec **`python3 -c`** :
```bash
python3 -c "print(not True)"  # Résultat : False
python3 -c "print(True and False)"  # Résultat : False
python3 -c "print(True or False)"  # Résultat : True
```

#### Dans le fichier `exercice_condition.py` :
1. Ajoutez ce code :
   ```python
   print(not True)  # Résultat : False
   print(True and False)  # Résultat : False
   print(True or False)  # Résultat : True
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_condition.py
   ```

3. **Résultat attendu** :
   ```plaintext
   False
   False
   True
   ```

---

### 2. Opérateurs d'égalité et de comparaison

#### Avec **`python3 -c`** :
```bash
python3 -c "print(5 == 5)"  # Résultat : True
python3 -c "print(5 != 3)"  # Résultat : True
python3 -c "print(7 > 5)"  # Résultat : True
python3 -c "print(5 <= 3)"  # Résultat : False
```

#### Dans le fichier `exercice_condition.py` :
1. Ajoutez ce code après le précédent :
   ```python
   print(5 == 5)  # Résultat : True
   print(5 != 3)  # Résultat : True
   print(7 > 5)  # Résultat : True
   print(5 <= 3)  # Résultat : False
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_condition.py
   ```

3. **Résultat attendu** :
   ```plaintext
   True
   True
   True
   False
   ```

---

### 3. Comparaison de chaînes de caractères

#### Avec **`python3 -c`** :
```bash
python3 -c "print('apple' < 'banana')"  # Résultat : True
python3 -c "print('Python' == 'python')"  # Résultat : False
```

#### Dans le fichier `exercice_condition.py` :
1. Ajoutez ce code :
   ```python
   print("apple" < "banana")  # Résultat : True
   print("Python" == "python")  # Résultat : False
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_condition.py
   ```

3. **Résultat attendu** :
   ```plaintext
   True
   False
   ```

---

### 4. Les structures conditionnelles

#### Avec **`python3 -c`** :
```bash
python3 -c "x = 10; print('x est supérieur à 5' if x > 5 else 'x est inférieur ou égal à 5')"
```

#### Dans le fichier `exercice_condition.py` :
1. Ajoutez ce code :
   ```python
   x = 10
   if x > 5:
       print("x est supérieur à 5")
   else:
       print("x est inférieur ou égal à 5")

   # Structure ternaire
   message = "x est supérieur à 5" if x > 5 else "x est inférieur ou égal à 5"
   print(message)
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_condition.py
   ```

3. **Résultat attendu** :
   ```plaintext
   x est supérieur à 5
   x est supérieur à 5
   ```

---

### 5. Exercice global : Vérification d'âge

#### Objectif :
Créer un programme qui demande un âge et affiche un message selon les conditions suivantes :
- Si l'âge est supérieur ou égal à 18, affichez : "Vous êtes majeur."
- Sinon, affichez : "Vous êtes mineur."

#### Avec **`python3 -c`** :
```bash
python3 -c "age = 20; print('Vous êtes majeur.' if age >= 18 else 'Vous êtes mineur.')"
```

#### Dans le fichier `exercice_condition.py` :
1. Ajoutez ce code :
   ```python
   age = int(input("Entrez votre âge : "))
   if age >= 18:
       print("Vous êtes majeur.")
   else:
       print("Vous êtes mineur.")
   ```

2. **Exécutez avec** :
   ```bash
   python3 exercice_condition.py
   ```

3. **Exemple de session** :
   ```plaintext
   Entrez votre âge : 17
   Vous êtes mineur.
   ```

---

## Résumé des commandes

1. **Créer un fichier Python** (facultatif) :
   - Windows :
     ```cmd
     notepad exercice_condition.py
     ```
   - Linux/macOS :
     ```bash
     nano exercice_condition.py
     ```

2. **Exécuter une commande Python directement** :
   ```bash
   python3 -c "print(True and False)"
   ```

3. **Exécuter un fichier Python** :
   ```bash
   python3 exercice_condition.py
   ```

4. **Activer/Désactiver un environnement virtuel** :
   - **Activer** :
     ```bash
     source pratique_env/bin/activate  # Linux/macOS
     pratique_env\Scripts\activate  # Windows
     ```
   - **Désactiver** :
     ```bash
     deactivate
     ```

