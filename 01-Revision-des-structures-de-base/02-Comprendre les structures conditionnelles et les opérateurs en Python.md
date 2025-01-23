# Comprendre les structures conditionnelles et les opérateurs en Python

## Introduction

Dans cette leçon, nous explorerons les concepts suivants :

1. Les opérateurs logiques et d’égalité
2. Les structures conditionnelles
3. Les comparaisons de chaînes de caractères

Ces notions sont essentielles pour écrire du code Python efficace et adapté à divers scénarios.

---

## 1. Les opérateurs logiques en Python

### Opérateur NOT
- **Description** : L’opérateur `not` inverse la valeur de vérité d’une expression.  
- **Exemple** :
  ```python
  print(not True)  # Résultat : False
  print(not False)  # Résultat : True
  ```

### Opérateur AND
- **Description** : `and` retourne `True` uniquement si toutes les expressions évaluées sont vraies.  
- **Exemple** :
  ```python
  print(True and True)  # Résultat : True
  print(True and False)  # Résultat : False
  ```

### Opérateur OR
- **Description** : `or` retourne `True` si au moins une des expressions évaluées est vraie.  
- **Exemple** :
  ```python
  print(True or False)  # Résultat : True
  print(False or False)  # Résultat : False
  ```

---

## 2. Les opérateurs d’égalité et de comparaison

### Égalité (`==`) et Différence (`!=`)
- **Description** : 
  - `==` compare si deux valeurs sont égales.
  - `!=` vérifie si elles sont différentes.
- **Exemple** :
  ```python
  print(5 == 5)  # Résultat : True
  print(5 != 3)  # Résultat : True
  ```

### Identité (`is`) et Non-identité (`is not`)
- **Description** : 
  - `is` vérifie si deux variables pointent vers le même objet en mémoire.
  - `is not` vérifie si elles pointent vers des objets différents.
- **Exemple** :
  ```python
  x = [1, 2]
  y = [1, 2]
  print(x is y)  # Résultat : False (listes différentes en mémoire)
  print(x is not y)  # Résultat : True
  ```

### Comparateurs numériques (`>`, `>=`, `<`, `<=`)
- **Description** :
  - Ces opérateurs comparent deux valeurs numériques.
- **Exemple** :
  ```python
  x = 7
  y = 5
  print(x > y)  # Résultat : True
  print(x <= y)  # Résultat : False
  ```

---

## 3. Comparaison de chaînes de caractères

### Lexicographie
Les chaînes sont comparées selon l’ordre Unicode des caractères.  
- **Exemple** :
  ```python
  print("apple" < "banana")  # Résultat : True
  print("apple" == "apple")  # Résultat : True
  ```

### Attention aux caractères spéciaux
Pour éviter des comparaisons incorrectes avec des caractères Unicode composés différemment, utilisez une normalisation :
- **Exemple** :
  ```python
  import unicodedata

  str1 = "école"
  str2 = "e\u0301cole"  # même texte avec un diacritique séparé

  str1_normalized = unicodedata.normalize("NFC", str1)
  str2_normalized = unicodedata.normalize("NFC", str2)
  print(str1_normalized == str2_normalized)  # Résultat : True
  ```

---

## 4. Les structures conditionnelles en Python

### Structure `if`
- **Description** : Permet d’exécuter un bloc de code si une condition est vraie.
- **Exemple** :
  ```python
  x = 10
  if x > 5:
      print("x est supérieur à 5")
  ```

### Structure `if...else`
- **Description** : Permet de gérer les cas où une condition est vraie ou fausse.
- **Exemple** :
  ```python
  x = 10
  if x > 5:
      print("x est supérieur à 5")
  else:
      print("x est inférieur ou égal à 5")
  ```

### Structure `if...elif...else`
- **Description** : Permet de gérer plusieurs conditions.
- **Exemple** :
  ```python
  x = 10
  if x > 15:
      print("x est supérieur à 15")
  elif x > 5:
      print("x est supérieur à 5 mais inférieur ou égal à 15")
  else:
      print("x est inférieur ou égal à 5")
  ```

### Structure ternaire
- **Description** : Permet de simplifier une condition sur une seule ligne.
- **Exemple** :
  ```python
  x = 10
  message = "x est supérieur à 5" if x > 5 else "x est inférieur ou égal à 5"
  print(message)
  ```

---

## Conclusion

Ces concepts fondamentaux sur les opérateurs, les comparateurs, et les structures conditionnelles sont indispensables pour écrire des programmes Python performants et robustes. En combinant ces outils, vous pouvez construire des logiques complexes et résoudre une large variété de problèmes.

---

### Ressources supplémentaires
- [Documentation officielle Python](https://docs.python.org/)
