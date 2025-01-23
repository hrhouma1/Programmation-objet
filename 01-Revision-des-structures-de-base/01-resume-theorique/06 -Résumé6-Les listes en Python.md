
# Résumé 6: Les listes en Python

## Introduction

Les listes sont des structures de données ordonnées et modifiables qui peuvent contenir différents types d'éléments.

---

## Points clés

### 1. **Créer une liste**
Une liste est définie avec des crochets `[ ]` et les éléments sont séparés par des virgules.

**Exemple :**
```python
ma_liste = [42, "Python", 3.14]
print(ma_liste)  # Affiche [42, 'Python', 3.14]
```

---

### 2. **Accéder aux éléments**
- **Indices positifs** : Le premier élément a l'indice `0`.
  ```python
  print(ma_liste[0])  # Affiche 42
  ```
- **Indices négatifs** : Permettent d’accéder à partir de la fin.
  ```python
  print(ma_liste[-1])  # Affiche 3.14
  ```
- **Listes imbriquées** : Utilisez plusieurs indices pour accéder aux sous-éléments.
  ```python
  liste = [[1, 2], ["a", "b"]]
  print(liste[1][0])  # Affiche "a"
  ```

---

### 3. **Modifier une liste**
- **Ajouter** : 
  - `append()` pour un élément.
  - `extend()` pour plusieurs éléments.
  ```python
  fruits = ["pomme"]
  fruits.append("orange")
  fruits.extend(["banane", "kiwi"])
  print(fruits)  # ['pomme', 'orange', 'banane', 'kiwi']
  ```

- **Supprimer** :
  - `remove()` pour supprimer un élément spécifique.
  - `pop()` pour supprimer à un indice.
  ```python
  fruits.remove("orange")
  fruits.pop(1)
  print(fruits)  # ['pomme', 'kiwi']
  ```

---

### 4. **Concaténer et répéter**
- **Concaténer** : Utilisez `+`.
  ```python
  liste1 = [1, 2]
  liste2 = [3, 4]
  print(liste1 + liste2)  # [1, 2, 3, 4]
  ```
- **Répéter** : Utilisez `*`.
  ```python
  print([1, 2] * 3)  # [1, 2, 1, 2, 1, 2]
  ```

---

### 5. **Parcourir une liste**
- Avec une boucle `for` :
  ```python
  couleurs = ["rouge", "vert"]
  for couleur in couleurs:
      print(couleur)  # "rouge", "vert"
  ```
- Avec `enumerate()` pour obtenir l’indice :
  ```python
  for i, couleur in enumerate(couleurs):
      print(f"Index {i} : {couleur}")
  ```

---

### 6. **Trancher une liste (slicing)**
- Extraire une sous-liste :
  ```python
  nombres = [0, 1, 2, 3, 4]
  print(nombres[1:4])  # [1, 2, 3]
  ```
- Inverser une liste :
  ```python
  print(nombres[::-1])  # [4, 3, 2, 1, 0]
  ```

---

### 7. **Méthodes utiles**
- `count()` : Compte les occurrences.
- `index()` : Trouve l’indice d’un élément.
- `sort()` : Trie la liste.
- `reverse()` : Inverse l’ordre.

**Exemple :**
```python
nombres = [3, 1, 4]
nombres.sort()
print(nombres)  # [1, 3, 4]
```

---

## Conclusion

Les listes sont des outils puissants et flexibles pour manipuler des données. Leur maîtrise permet de résoudre efficacement divers problèmes.

---

### Ressources
- [Documentation Python : Listes](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)
