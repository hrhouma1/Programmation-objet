
# Résumé : Structures conditionnelles et opérateurs en Python

## Introduction

Les structures conditionnelles et les opérateurs sont essentiels pour créer des programmes capables de prendre des décisions en fonction des données ou des conditions.

---

## Points clés

### 1. **Opérateurs logiques**
- `not` : Inverse une condition.
- `and` : Retourne `True` si toutes les conditions sont vraies.
- `or` : Retourne `True` si au moins une condition est vraie.

**Exemple :**
```python
print(not True)  # False
print(True and False)  # False
print(True or False)  # True
```

---

### 2. **Opérateurs d’égalité et de comparaison**
- `==` : Compare si deux valeurs sont égales.
- `!=` : Vérifie si deux valeurs sont différentes.
- `>`, `<`, `>=`, `<=` : Comparent deux nombres.
- `is`, `is not` : Vérifient si deux variables pointent vers le même objet en mémoire.

**Exemple :**
```python
print(5 == 5)  # True
print(5 > 3)  # True
```

---

### 3. **Comparaison de chaînes de caractères**
- Les chaînes sont comparées selon l’ordre Unicode (ordre alphabétique).
- Pour une comparaison correcte avec des caractères spéciaux, utilisez la **normalisation Unicode**.

**Exemple :**
```python
import unicodedata
str1 = "école"
str2 = "e\u0301cole"  # "é" représenté différemment
print(unicodedata.normalize("NFC", str1) == unicodedata.normalize("NFC", str2))  # True
```

---

### 4. **Structures conditionnelles**
#### a) `if`
Exécute un bloc de code si une condition est vraie.
```python
x = 10
if x > 5:
    print("x est supérieur à 5")
```

#### b) `if...else`
Gère un bloc si la condition est fausse.
```python
x = 3
if x > 5:
    print("x est supérieur à 5")
else:
    print("x est inférieur ou égal à 5")
```

#### c) `if...elif...else`
Vérifie plusieurs conditions.
```python
x = 10
if x > 15:
    print("x est supérieur à 15")
elif x > 5:
    print("x est supérieur à 5")
else:
    print("x est inférieur ou égal à 5")
```

#### d) Structure ternaire
Simplifie une condition en une seule ligne.
```python
message = "x est positif" if x > 0 else "x est négatif ou nul"
print(message)
```

---

## Conclusion

Les structures conditionnelles et les opérateurs permettent de construire des programmes intelligents et interactifs. En les combinant, vous pouvez gérer des scénarios complexes avec efficacité.

---

### Ressources
- [Documentation Python](https://docs.python.org/)
