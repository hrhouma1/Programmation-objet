# Les listes en Python

## Introduction

Une liste est une structure de données qui permet de stocker une collection d'éléments dans un ordre spécifique. Les listes en Python sont **modifiables**, **ordonnées**, et peuvent contenir des éléments de types différents.

---

## 1. Créer une liste

Les listes sont définies avec des crochets `[ ]`, et les éléments sont séparés par des virgules.

```python
ma_liste = [42, "Python", 3.14, False]
print(ma_liste)  # Affiche [42, 'Python', 3.14, False]
```

Dans cet exemple, la liste contient un entier, une chaîne de caractères, un nombre à virgule flottante et un booléen.

---

## 2. Accéder aux éléments d'une liste

### Avec des indices positifs
Les indices commencent à `0`. Le premier élément a l’indice `0`, le deuxième `1`, et ainsi de suite.

```python
animaux = ["chien", "chat", "lapin"]
print(animaux[0])  # Affiche "chien"
print(animaux[1])  # Affiche "chat"
```

### Avec des indices négatifs
Les indices négatifs permettent d’accéder aux éléments en partant de la fin de la liste.

```python
animaux = ["chien", "chat", "lapin"]
print(animaux[-1])  # Affiche "lapin" (dernier élément)
print(animaux[-2])  # Affiche "chat"
```

### Listes imbriquées
Les listes peuvent contenir d’autres listes. Accédez aux sous-éléments en utilisant des indices multiples.

```python
donnees = [[1, 2], ["a", "b"], [True, False]]
print(donnees[1][0])  # Affiche "a" (premier élément de la deuxième liste)
print(donnees[2][1])  # Affiche False
```

---

## 3. Modifier une liste

### Ajouter des éléments
- **append()** : Ajoute un élément à la fin.
- **extend()** : Ajoute plusieurs éléments à la fin.

```python
fruits = ["pomme", "orange"]
fruits.append("banane")
print(fruits)  # Affiche ['pomme', 'orange', 'banane']

fruits.extend(["kiwi", "mangue"])
print(fruits)  # Affiche ['pomme', 'orange', 'banane', 'kiwi', 'mangue']
```

### Supprimer des éléments
- **remove()** : Supprime la première occurrence d’un élément.
- **pop()** : Supprime un élément à un indice donné (par défaut, le dernier).

```python
fruits = ["pomme", "orange", "banane"]
fruits.remove("orange")
print(fruits)  # Affiche ['pomme', 'banane']

fruits.pop(1)  # Supprime "banane"
print(fruits)  # Affiche ['pomme']
```

---

## 4. Concaténer et répéter des listes

### Concaténation avec `+`
```python
liste1 = [1, 2]
liste2 = [3, 4]
resultat = liste1 + liste2
print(resultat)  # Affiche [1, 2, 3, 4]
```

### Répétition avec `*`
```python
liste = ["A", "B"]
repetition = liste * 3
print(repetition)  # Affiche ['A', 'B', 'A', 'B', 'A', 'B']
```

---

## 5. Parcourir une liste

### Avec une boucle `for`
```python
couleurs = ["rouge", "vert", "bleu"]
for couleur in couleurs:
    print(couleur)
# Affiche "rouge", "vert", "bleu"
```

### Avec `range()` et `len()`
```python
couleurs = ["rouge", "vert", "bleu"]
for i in range(len(couleurs)):
    print(f"Index {i} : {couleurs[i]}")
# Affiche "Index 0 : rouge", "Index 1 : vert", "Index 2 : bleu"
```

### Avec `enumerate()`
```python
couleurs = ["rouge", "vert", "bleu"]
for indice, valeur in enumerate(couleurs):
    print(f"Index {indice} : {valeur}")
# Affiche "Index 0 : rouge", "Index 1 : vert", "Index 2 : bleu"
```

---

## 6. Trancher une liste (slicing)

### Obtenir une sous-liste
La notation `[debut:fin:pas]` permet d'extraire une partie de la liste.

```python
nombres = [0, 1, 2, 3, 4, 5]
print(nombres[1:4])  # Affiche [1, 2, 3]
print(nombres[:3])   # Affiche [0, 1, 2] (jusqu’à l'indice 3 exclus)
print(nombres[::2])  # Affiche [0, 2, 4] (pas de 2)
```

### Inverser une liste
Utilisez un pas négatif pour inverser l'ordre.

```python
nombres = [1, 2, 3, 4, 5]
print(nombres[::-1])  # Affiche [5, 4, 3, 2, 1]
```

---

## 7. Méthodes utiles pour les listes

- **count()** : Compte le nombre d’occurrences d’un élément.
- **index()** : Trouve la position d’un élément.
- **sort()** : Trie la liste.
- **reverse()** : Inverse l’ordre de la liste.

### Exemples :
```python
nombres = [3, 1, 4, 1, 5]
print(nombres.count(1))  # Affiche 2
print(nombres.index(4))  # Affiche 2

nombres.sort()
print(nombres)  # Affiche [1, 1, 3, 4, 5]

nombres.reverse()
print(nombres)  # Affiche [5, 4, 3, 1, 1]
```

---

## Conclusion

Les listes sont un outil polyvalent pour gérer des collections de données en Python. Leur flexibilité et leur richesse en fonctionnalités permettent de résoudre une grande variété de problèmes.

---

## Ressources supplémentaires
- [Documentation officielle sur les listes Python](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)
