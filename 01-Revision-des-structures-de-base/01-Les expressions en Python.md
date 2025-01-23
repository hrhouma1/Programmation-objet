# Les expressions en Python

## Introduction

Dans cette leçon, nous allons explorer les bases de la programmation en Python, notamment :

1. **Les expressions**
2. **Les opérateurs courants**
3. **Les types de données**

---

## 1. Qu'est-ce qu'une expression en Python ?

Une expression est une combinaison de **variables**, de **valeurs constantes**, d'**opérateurs** et de **fonctions**, qui produit une valeur.

### Exemple d'expressions simples :

```python
3 + 5          # Addition
"Hello" + " World"  # Concaténation de chaînes
5 * (2 + 3)    # Expression arithmétique
len("Python")  # Appel d'une fonction
```

### Règles importantes :
- Les expressions sont évaluées **de gauche à droite**, tout en respectant la **priorité des opérateurs**.

---

## 2. Les opérateurs courants

Les opérateurs permettent d'exécuter des opérations sur des variables et des valeurs. Voici les principales catégories :

### 2.1 Opérateurs arithmétiques

- `+` : Addition  
  Exemple : `3 + 2` retourne `5`
- `-` : Soustraction  
  Exemple : `5 - 2` retourne `3`
- `*` : Multiplication  
  Exemple : `4 * 3` retourne `12`
- `/` : Division  
  Exemple : `10 / 2` retourne `5.0`
- `//` : Division entière (résultat sans décimales)  
  Exemple : `10 // 3` retourne `3`
- `%` : Modulo (reste de la division)  
  Exemple : `10 % 3` retourne `1`
- `**` : Puissance  
  Exemple : `2 ** 3` retourne `8`

### 2.2 Opérateurs de comparaison

- `==` : Égal à  
  Exemple : `5 == 5` retourne `True`
- `!=` : Différent de  
  Exemple : `5 != 3` retourne `True`
- `>` : Supérieur à  
  Exemple : `5 > 3` retourne `True`
- `<` : Inférieur à  
  Exemple : `3 < 5` retourne `True`
- `>=` : Supérieur ou égal à  
  Exemple : `5 >= 5` retourne `True`
- `<=` : Inférieur ou égal à  
  Exemple : `3 <= 5` retourne `True`

### 2.3 Opérateurs logiques

- `and` : Retourne `True` si **toutes** les conditions sont vraies  
  Exemple : `(5 > 3) and (3 < 10)` retourne `True`
- `or` : Retourne `True` si **au moins une** condition est vraie  
  Exemple : `(5 > 3) or (3 > 10)` retourne `True`
- `not` : Inverse la condition  
  Exemple : `not (5 > 3)` retourne `False`

### 2.4 Opérateurs d'appartenance

- `in` : Vérifie si un élément appartient à une séquence  
  Exemple : `'a' in 'apple'` retourne `True`
- `not in` : Vérifie si un élément **n'appartient pas** à une séquence  
  Exemple : `'b' not in 'apple'` retourne `True`

---

## 3. Types de données en Python

Python propose plusieurs types de données fondamentaux. Voici les plus courants :

### 3.1 Types numériques

- `int` : Représente les nombres entiers.  
  Exemple :  
  ```python
  x = 5  # x est un entier
  ```

- `float` : Représente les nombres décimaux.  
  Exemple :  
  ```python
  y = 3.14  # y est un nombre flottant
  ```

### 3.2 Chaînes de caractères (`str`)

Les chaînes sont utilisées pour représenter du texte.

Exemples :  
```python
nom = "Python"
salutation = 'Bonjour'
texte_multi_ligne = """Ceci est
un texte multi-ligne."""
```

### 3.3 Types séquentiels

- `list` : Liste modifiable.  
  Exemple :  
  ```python
  [1, 2, 3]
  ```

- `tuple` : Tuple immuable (non modifiable).  
  Exemple :  
  ```python
  (1, 2, 3)
  ```

### 3.4 Dictionnaires (`dict`)

Un dictionnaire contient des **paires clé-valeur**.  
Exemple :  
```python
{"nom": "Alice", "age": 25}
```

### 3.5 Ensembles (`set`)

Un ensemble contient des éléments **uniques** et **non ordonnés**.  
Exemple :  
```python
{1, 2, 3}
```

### 3.6 Booléens (`bool`)

Les booléens peuvent être `True` (vrai) ou `False` (faux).  
Exemple :  
```python
actif = True
termine = False
```

---

## Conclusion

Ces bases constituent les **fondations** de la programmation en Python. La maîtrise des expressions, des opérateurs, et des types de données est essentielle pour écrire du code lisible et fonctionnel.

---

## Ressources supplémentaires

- [Documentation officielle Python](https://docs.python.org/)
