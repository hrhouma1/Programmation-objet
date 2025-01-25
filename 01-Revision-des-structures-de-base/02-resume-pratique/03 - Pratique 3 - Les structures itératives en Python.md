Voici la version corrigée en utilisant des fichiers distincts pour chaque exercice, comme demandé :

---

# Pratique 3 : Les structures itératives en Python

## Table des matières

1. [Objectif](#objectif)  
2. [Note préalable](#note-préalable)  
3. [Préparation](#préparation)  
4. [Exercices](#exercices)  
   - [Exercice 1 : La boucle `while`](#exercice-1--la-boucle-while)  
   - [Exercice 2 : Entrée utilisateur avec `while`](#exercice-2--entrée-utilisateur-avec-while)  
   - [Exercice 3 : La boucle `for`](#exercice-3--la-boucle-for)  
   - [Exercice 4 : Utilisation de `range`](#exercice-4--utilisation-de-range)  
   - [Exercice 5 : Boucles imbriquées](#exercice-5--boucles-imbriquées)  
   - [Exercice 6 : Exercice global - Table de multiplication](#exercice-6--exercice-global---table-de-multiplication)  
5. [Annexe : Exécution rapide avec `python -c`](#annexe--exécution-rapide-avec-python--c)

---

## Objectif
Pratiquer les structures itératives en Python, notamment les boucles `while` et `for`, en écrivant et exécutant du code dans des fichiers Python.

---

## Note préalable
Le module `venv` est inclus par défaut dans Python 3.3 et versions ultérieures.  
- **Si `venv` n'est pas disponible**, installez-le avec :
  ```bash
  pip install venv
  ```
- **Pour plusieurs versions de Python installées**, utilisez des commandes spécifiques : `python3.11`, `python3.12`, etc.

---

## Préparation

1. **Créer un environnement virtuel** :  
   ```bash
   python -m venv pratique3
   pratique3\Scripts\activate
   ```

2. **Créer plusieurs fichiers Python** :  
   ```cmd
   notepad exercice1.py   # Fichier pour l'exercice 1
   notepad exercice2.py   # Fichier pour l'exercice 2
   notepad exercice3.py   # Fichier pour l'exercice 3
   notepad exercice4.py   # Fichier pour l'exercice 4
   notepad exercice5.py   # Fichier pour l'exercice 5
   notepad exercice6.py   # Fichier pour l'exercice 6
   ```

---

## Exercices

### Exercice 1 : La boucle `while`
Ajoutez ce code dans `exercice1.py` :
```python
compteur = 1
while compteur <= 5:
    print(compteur)
    compteur += 1
```

---

### Exercice 2 : Entrée utilisateur avec `while`
Ajoutez ce code dans `exercice2.py` :
```python
nombre = 0
while nombre <= 0:
    nombre = int(input("Veuillez entrer un nombre supérieur à zéro : "))
print(f"Vous avez entré {nombre}. Merci !")
```

---

### Exercice 3 : La boucle `for`
Ajoutez ce code dans `exercice3.py` :
```python
animaux = ["chat", "chien", "oiseau"]
for animal in animaux:
    print(animal)
```

---

### Exercice 4 : Utilisation de `range`
Ajoutez ce code dans `exercice4.py` :
```python
for nombre in range(1, 6):
    print(nombre)
```

---

### Exercice 5 : Boucles imbriquées
Ajoutez ce code dans `exercice5.py` :
```python
taille = 4
for i in range(taille):
    for j in range(taille):
        print("#", end="")
    print()
```

---

### Exercice 6 : Exercice global - Table de multiplication
Ajoutez ce code dans `exercice6.py` :
```python
for i in range(1, 6):
    for j in range(1, 6):
        print(f"{i * j:2}", end=" ")
    print()
```

---

## Annexe : Exécution rapide avec `python -c`

### Méthode
Pour tester rapidement des expressions ou des structures, utilisez `python -c`.

### Exemples
- **Exercice 1 : La boucle `while`**  
  ```bash
  python -c "
compteur = 1
while compteur <= 5:
    print(compteur)
    compteur += 1
"
  ```
- **Exercice 2 : Entrée utilisateur avec `while`**  
  ```bash
  python -c "
nombre = 0
while nombre <= 0:
    nombre = int(input('Veuillez entrer un nombre supérieur à zéro : '))
print(f'Vous avez entré {nombre}. Merci !')
"
  ```
- **Exercice 3 : La boucle `for`**  
  ```bash
  python -c "
animaux = ['chat', 'chien', 'oiseau']
for animal in animaux:
    print(animal)
"
  ```
- **Exercice 4 : Utilisation de `range`**  
  ```bash
  python -c "
for nombre in range(1, 6):
    print(nombre)
"
  ```
- **Exercice 5 : Boucles imbriquées**  
  ```bash
  python -c "
taille = 4
for i in range(taille):
    for j in range(taille):
        print('#', end='')
    print()
"
  ```
- **Exercice 6 : Table de multiplication**  
  ```bash
  python -c "
for i in range(1, 6):
    for j in range(1, 6):
        print(f'{i * j:2}', end=' ')
    print()
"
  ```

---

### Résumé
- **Pour des scripts détaillés**, utilisez des fichiers Python comme `exercice1.py`, `exercice2.py`, etc.
- **Pour tester rapidement des concepts**, utilisez `python -c`.
