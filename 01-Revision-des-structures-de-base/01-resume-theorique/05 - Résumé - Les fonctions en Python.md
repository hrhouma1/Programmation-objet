# Résumé : Les fonctions en Python

## Introduction

Les fonctions sont des blocs de code qui effectuent des tâches spécifiques. Elles rendent le code plus **lisible**, **réutilisable**, et **facile à maintenir**.

---

## Points clés

### 1. **Définir une fonction**
- Une fonction est définie avec le mot-clé `def`.
- Elle peut avoir des paramètres (facultatifs) et retourner des valeurs.

**Exemple :**
```python
def saluer(nom="ami"):
    print(f"Bonjour, {nom} !")

saluer()  # "Bonjour, ami !"
saluer("Alice")  # "Bonjour, Alice !"
```

---

### 2. **Retourner des valeurs**
Une fonction peut retourner une ou plusieurs valeurs avec `return`.

**Exemple :**
```python
def calculer(valeur):
    return valeur ** 2, valeur ** 3

carre, cube = calculer(3)
print(carre, cube)  # 9, 27
```

---

### 3. **Arguments variables**
Utilisez `*args` pour accepter un nombre variable d'arguments.

**Exemple :**
```python
def additionner(*nombres):
    return sum(nombres)

print(additionner(1, 2, 3))  # 6
```

Pour des arguments nommés, utilisez `**kwargs`.
```python
def afficher_infos(**infos):
    for cle, valeur en infos.items():
        print(f"{cle} : {valeur}")

afficher_infos(nom="Marie", age=30)  # nom : Marie, age : 30
```

---

### 4. **Portée des variables**
- **Variables locales** : Définies dans une fonction et accessibles uniquement à l’intérieur.
- **Variables globales** : Définies en dehors et accessibles partout, mais doivent être modifiées avec `global`.

**Exemple :**
```python
x = 5  # Globale
def changer():
    global x
    x = 10
changer()
print(x)  # 10
```

---

### 5. **Fonctions imbriquées**
Une fonction peut appeler une autre pour diviser une tâche complexe.

**Exemple :**
```python
def faire_du_the():
    def chauffer_eau(temp):
        return f"Eau chauffée à {temp}°C"
    print(chauffer_eau(100))

faire_du_the()  # Eau chauffée à 100°C
```

---

## Conclusion

Les fonctions permettent de structurer le code et de le rendre modulaire. Maîtriser leur syntaxe et leurs usages avancés est essentiel pour écrire du code Python efficace.

---

### Ressources
- [Documentation Python sur les fonctions](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)
