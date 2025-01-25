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

## Préparation

1. **Créer un environnement virtuel** :  
   ```bash
   python -m venv pratique_env
   pratique_env\Scripts\activate
   ```

2. **Créer un fichier Python** :  
   ```cmd
   notepad exercice_condition.py
   ```

---

## Exercices

### Exercice 1 : Opérateurs logiques
Ajoutez ce code dans `exercice_condition.py` :
```python
print(not True)  # False
print(True and False)  # False
print(True or False)  # True
```

---

### Exercice 2 : Opérateurs de comparaison
Ajoutez ce code dans `exercice_condition.py` :
```python
print(5 == 5)  # True
print(7 > 5)  # True
print(5 <= 3)  # False
```

---

### Exercice 3 : Comparaison de chaînes
Ajoutez ce code dans `exercice_condition.py` :
```python
print("apple" < "banana")  # True
print("Python" == "python")  # False
```

---

### Exercice 4 : Structures conditionnelles
Ajoutez ce code dans `exercice_condition.py` :
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
Ajoutez ce code dans `exercice_condition.py` :
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
