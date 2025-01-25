# Pratique 2 - Structures conditionnelles et opérateurs en Python

## Table des matières

1. [Objectif](#objectif)  
2. [Préparation](#préparation)  
3. [Exercices](#exercices)  
   - [Exercice 1 : Opérateurs logiques](#exercice-1--opérateurs-logiques)  
   - [Exercice 2 : Opérateurs de comparaison](#exercice-2--opérateurs-de-comparaison)  
   - [Exercice 3 : Comparaison de chaînes](#exercice-3--comparaison-de-chaînes)  
   - [Exercice 4 : Structures conditionnelles](#exercice-4--structures-conditionnelles)  
   - [Exercice 5 : Vérification d'âge](#exercice-5--vérification-dâge)  
4. [Annexe : Exécution rapide avec `python -c`](#annexe--exécution-rapide-avec-python--c)

---

## Objectif
Pratiquer les opérateurs logiques, de comparaison, et les structures conditionnelles en Python en écrivant et exécutant du code dans des fichiers Python.


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

1. **Créer un environnement virtuel** :  
   ```bash
   python -m venv pratique2
   pratique2\Scripts\activate
   ```

2. **Créer plusieurs fichiers Python** :  
   ```cmd
   notepad exemple1.py   # Fichier pour l'exercice 1
   notepad exemple2.py   # Fichier pour l'exercice 2
   notepad exemple3.py   # Fichier pour l'exercice 3
   notepad exemple4.py   # Fichier pour l'exercice 4
   notepad exemple5.py   # Fichier pour l'exercice 5
   ```

---

## Exercices

### Exercice 1 : Opérateurs logiques
Ajoutez ce code dans `exemple1.py` :
```python
print(not True)  # False
print(True and False)  # False
print(True or False)  # True
```

---

### Exercice 2 : Opérateurs de comparaison
Ajoutez ce code dans `exemple2.py` :
```python
print(5 == 5)  # True
print(7 > 5)  # True
print(5 <= 3)  # False
```

---

### Exercice 3 : Comparaison de chaînes
Ajoutez ce code dans `exemple3.py` :
```python
print("apple" < "banana")  # True
print("Python" == "python")  # False
```

---

### Exercice 4 : Structures conditionnelles
Ajoutez ce code dans `exemple4.py` :
```python
x = 10
if x > 5:
    print("x est supérieur à 5")
else:
    print("x est inférieur ou égal à 5")

# Utilisation d'une structure ternaire
message = "x est supérieur à 5" if x > 5 else "x est inférieur ou égal à 5"
print(message)
```

---

### Exercice 5 : Vérification d'âge
Ajoutez ce code dans `exemple5.py` :
```python
age = int(input("Entrez votre âge : "))
if age >= 18:
    print("Vous êtes majeur.")
else:
    print("Vous êtes mineur.")
```

---

## Annexe : Exécution rapide avec `python -c`

### Méthode
Pour tester rapidement des expressions ou des structures, utilisez `python -c`.

### Exemples
- **Exercice 1 : Opérateurs logiques**  
  ```bash
  python -c "print(not True)"  # False
  ```
- **Exercice 2 : Opérateurs de comparaison**  
  ```bash
  python -c "print(5 == 5)"  # True
  ```
- **Exercice 3 : Comparaison de chaînes**  
  ```bash
  python -c "print('apple' < 'banana')"  # True
  ```
- **Exercice 4 : Structures conditionnelles**  
  ```bash
  python -c "x=10; print('Supérieur' if x>5 else 'Inférieur')"
  ```
- **Exercice 5 : Vérification d'âge**  
  ```bash
  python -c "age=20; print('Majeur' if age>=18 else 'Mineur')"
  ```

---

### Résumé
- Écrivez vos scripts dans des fichiers pour des exercices détaillés.
- Utilisez `python -c` pour tester rapidement des expressions ou concepts simples.
