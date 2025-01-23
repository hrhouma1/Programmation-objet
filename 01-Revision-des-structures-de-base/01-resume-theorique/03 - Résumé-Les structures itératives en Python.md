# Résumé : Les structures itératives en Python

## Introduction

Les structures itératives permettent de répéter des instructions en fonction d’une condition ou d’une séquence. Python offre deux types de boucles principales : **`while`** et **`for`**.

---

## Points clés

### 1. **La boucle `while`**
- Répète un bloc de code tant qu’une condition est vraie.
- La condition est vérifiée avant chaque itération.

**Exemple :** Afficher les nombres de 1 à 5.
```python
compteur = 1
while compteur <= 5:
    print(compteur)
    compteur += 1
```

**Utilisation :**
- Préférez `while` quand le nombre d’itérations n’est pas connu à l’avance (par exemple, demander des données utilisateur).

**Attention :**
- Évitez les boucles infinies en vous assurant que la condition devient fausse à un moment donné.
- Vous pouvez utiliser `break` pour sortir d’une boucle infinie.

---

### 2. **La boucle `for`**
- Itère sur une séquence comme une liste, un ensemble, ou une plage de nombres générée avec `range()`.

**Exemple :** Parcourir une liste d’animaux.
```python
animaux = ["chat", "chien", "oiseau"]
for animal in animaux:
    print(animal)
```

**Avec `range()` :** Générer des nombres.
```python
for nombre in range(1, 6):
    print(nombre)  # Affiche les nombres de 1 à 5
```

---

### 3. **Boucles imbriquées**
- Les boucles imbriquées permettent de parcourir des structures complexes ou de générer des motifs.

**Exemple :** Carré de caractères.
```python
taille = 3
for i in range(taille):
    for j in range(taille):
        print("#", end="")
    print()  # Ajoute une nouvelle ligne
```

**Exemple :** Triangle de caractères.
```python
hauteur = 3
for i in range(hauteur):
    for j in range(i + 1):
        print("*", end="")
    print()
```

---

## Conseils et bonnes pratiques

- **Utilisez `for`** lorsque le nombre d’itérations est connu à l’avance.
- **Évitez de modifier directement une séquence** sur laquelle vous itérez. Copiez-la si nécessaire.
- **Simplifiez vos boucles imbriquées** en utilisant des fonctions pour rendre votre code plus lisible.

---

## Conclusion

Les boucles `while` et `for` sont essentielles pour automatiser des tâches répétitives. Leur compréhension vous permettra d’écrire des programmes plus efficaces et dynamiques.

---

### Ressources
- [Documentation Python : Boucles](https://docs.python.org/3/tutorial/controlflow.html#for-statements)
