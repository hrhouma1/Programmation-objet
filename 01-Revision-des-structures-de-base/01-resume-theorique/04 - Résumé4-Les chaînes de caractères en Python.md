# Résumé 4: Les chaînes de caractères en Python

## Introduction

Les chaînes de caractères sont des séquences de texte immuables en Python. Elles offrent de nombreuses fonctionnalités pour les manipuler, les transformer, et les analyser.

---

## Points clés

### 1. **Concaténation de chaînes**
Joindre deux ou plusieurs chaînes avec l’opérateur `+`.
```python
prenom = "Alice"
nom = "Martin"
print(prenom + " " + nom)  # Affiche "Alice Martin"
```

---

### 2. **Interpolation de chaînes**
- **f-strings** : Insérer des variables ou expressions directement dans une chaîne.
  ```python
  ville = "Paris"
  print(f"Bienvenue à {ville} !")  # Affiche "Bienvenue à Paris !"
  ```
- **`format()`** : Alternative pour insérer des valeurs.
  ```python
  age = 25
  print("J'ai {} ans.".format(age))  # Affiche "J'ai 25 ans."
  ```

---

### 3. **Indexation et extraction**
- **Accès à un caractère** :
  ```python
  texte = "Python"
  print(texte[0])  # Premier caractère : "P"
  print(texte[-1])  # Dernier caractère : "n"
  ```
- **Slicing** : Extraire une sous-chaîne.
  ```python
  texte = "Programmation"
  print(texte[:5])  # "Progr"
  print(texte[::-1])  # "noitammargorP" (inverse)
  ```

---

### 4. **Méthodes courantes**
- **Changer la casse** :
  ```python
  texte = "Bonjour"
  print(texte.upper())  # "BONJOUR"
  print(texte.lower())  # "bonjour"
  ```
- **Supprimer les espaces** :
  ```python
  texte = "  Python  "
  print(texte.strip())  # "Python"
  ```
- **Rechercher et remplacer** :
  ```python
  texte = "Apprendre Python"
  print(texte.find("Python"))  # Index : 9
  print(texte.replace("Python", "la programmation"))  # "Apprendre la programmation"
  ```
- **Découper et assembler** :
  ```python
  phrase = "Python est génial"
  mots = phrase.split(" ")
  print(" ".join(mots))  # "Python est génial"
  ```
- **Compter les occurrences** :
  ```python
  texte = "Programmation Python"
  print(texte.count("o"))  # 3
  ```

---

### 5. **Cas spéciaux**
- **Omettre début ou fin avec slicing** :
  ```python
  texte = "Innovation"
  print(texte[:5])  # "Innov"
  print(texte[5:])  # "ation"
  ```
- **Inverser une chaîne** :
  ```python
  texte = "Palindrome"
  print(texte[::-1])  # "emordnilaP"
  ```

---

## Conclusion

Les chaînes de caractères en Python sont puissantes et flexibles. En combinant les méthodes et techniques décrites, vous pouvez manipuler du texte de manière efficace.

---

### Ressources
- [Documentation Python sur les chaînes](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)
