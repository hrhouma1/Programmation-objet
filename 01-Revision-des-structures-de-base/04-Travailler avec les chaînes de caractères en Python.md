# Les chaînes de caractères en Python

## Introduction

Les chaînes de caractères sont des séquences immuables utilisées pour représenter du texte. Python offre de nombreuses fonctionnalités pour manipuler et transformer les chaînes, que nous explorerons ici.

---

## 1. Concaténation de chaînes

La concaténation consiste à joindre deux ou plusieurs chaînes pour former une nouvelle chaîne.

### Exemple :
```python
prenom = "Alice"
nom = "Martin"
nom_complet = prenom + " " + nom
print(nom_complet)  # Affiche "Alice Martin"
```

---

## 2. Interpolation de chaînes

### a) Utilisation des f-strings
Les f-strings permettent d'insérer des variables ou des expressions directement dans une chaîne en les entourant d'accolades `{}`.

```python
ville = "Paris"
message = f"Bienvenue à {ville} !"
print(message)  # Affiche "Bienvenue à Paris !"
```

### b) Méthode `.format()`
Avant les f-strings, la méthode `format` était utilisée pour insérer des valeurs dans des chaînes.

```python
age = 25
message = "J'ai {} ans.".format(age)
print(message)  # Affiche "J'ai 25 ans."
```

---

## 3. Indexation et extraction de sous-chaînes

### Accès à un caractère
Les chaînes sont indexées, ce qui permet d'accéder à un caractère spécifique.

```python
texte = "Python"
print(texte[0])  # Affiche "P" (premier caractère)
print(texte[-1])  # Affiche "n" (dernier caractère)
```

### Extraction de sous-chaînes (slicing)
Utilisez la notation `[début:fin:pas]` pour extraire une sous-chaîne.

```python
texte = "Programmation"
print(texte[0:5])  # Affiche "Progr"
print(texte[::2])  # Affiche "Pormto" (saut de 2 caractères)
print(texte[::-1])  # Affiche "noitammargorP" (ordre inverse)
```

---

## 4. Méthodes courantes des chaînes

### a) Transformation de casse
- `upper()` : Convertit la chaîne en majuscules.
- `lower()` : Convertit la chaîne en minuscules.

```python
texte = "Bonjour"
print(texte.upper())  # Affiche "BONJOUR"
print(texte.lower())  # Affiche "bonjour"
```

### b) Suppression d'espaces inutiles
- `strip()` : Supprime les espaces en début et fin de chaîne.

```python
texte = "  Python  "
print(texte.strip())  # Affiche "Python"
```

### c) Recherche et remplacement
- `find()` : Renvoie l'indice de la première occurrence d'une sous-chaîne.
- `replace()` : Remplace une sous-chaîne par une autre.

```python
texte = "Apprendre Python est amusant."
print(texte.find("Python"))  # Affiche 9
print(texte.replace("Python", "la programmation"))  # "Apprendre la programmation est amusant."
```

### d) Découpage et assemblage
- `split()` : Divise une chaîne en une liste.
- `join()` : Assemble une liste de chaînes en une seule chaîne.

```python
phrase = "Python est génial"
mots = phrase.split(" ")
print(mots)  # Affiche ['Python', 'est', 'génial']

nouvelle_phrase = " ".join(mots)
print(nouvelle_phrase)  # Affiche "Python est génial"
```

### e) Comptage
- `count()` : Compte le nombre d'occurrences d'une sous-chaîne.

```python
texte = "Programmation Python"
print(texte.count("o"))  # Affiche 3
```

---

## 5. Cas spéciaux

### Slicing avancé
Vous pouvez omettre le début ou la fin pour extraire toute une partie de la chaîne.

```python
texte = "Innovation"
print(texte[:5])  # Affiche "Innov"
print(texte[5:])  # Affiche "ation"
```

### Manipulation de chaînes inversées
Utilisez un pas négatif pour inverser une chaîne.

```python
texte = "Palindrome"
print(texte[::-1])  # Affiche "emordnilaP"
```

---

## Conclusion

Les chaînes de caractères en Python offrent une richesse d'outils pour manipuler et transformer du texte. En combinant ces fonctionnalités, vous pouvez écrire du code efficace et lisible.

---

## Ressources supplémentaires
- [Documentation officielle Python sur les chaînes de caractères](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)

