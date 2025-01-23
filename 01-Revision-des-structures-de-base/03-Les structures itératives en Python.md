# Les structures itératives en Python

## Introduction

Les structures itératives permettent de répéter un bloc de code plusieurs fois, en fonction de conditions ou d'une séquence. Python offre deux structures principales : la boucle `while` et la boucle `for`.

---

## 1. La boucle `while`

La boucle `while` exécute un bloc de code tant qu'une condition reste vraie. La condition est vérifiée avant chaque itération.

### Syntaxe

```python
while condition:
    # bloc de code à exécuter
```

### Exemple 1 : Compter jusqu'à 5
Cet exemple affiche les nombres de 1 à 5 :

```python
compteur = 1
while compteur <= 5:
    print(compteur)
    compteur += 1
```

### Exemple 2 : Demander une entrée utilisateur
Cet exemple demande à l'utilisateur d'entrer un nombre supérieur à zéro :

```python
nombre = 0
while nombre <= 0:
    nombre = int(input("Veuillez entrer un nombre supérieur à zéro : "))
print(f"Vous avez entré {nombre}. Merci !")
```

### Conseil : Quand utiliser `while` ?
Utilisez une boucle `while` lorsque vous ne savez pas à l'avance combien d'itérations seront nécessaires, comme pour des calculs basés sur une condition dynamique.

#### Exemple : Doubler un investissement
Si vous investissez 500$ avec un rendement annuel de 4%, combien d'années faut-il pour atteindre 1000$ ?

```python
investissement = 500
objectif = 1000
taux = 0.04
annees = 0

while investissement < objectif:
    investissement *= 1 + taux
    annees += 1

print(f"Votre investissement atteindra {objectif}$ en {annees} années.")
```

### Attention aux boucles infinies
Une boucle infinie se produit si la condition reste toujours vraie. Par exemple :

```python
i = 0
while i >= 0:  # La condition ne devient jamais fausse
    print("Cela ne s'arrêtera jamais !")
```

Pour éviter cela, assurez-vous que la condition change ou utilisez une instruction `break` :

```python
i = 0
while True:  # Boucle potentiellement infinie
    print(i)
    i += 1
    if i >= 10:  # Sortie forcée
        break
```

---

## 2. La boucle `for`

La boucle `for` itère sur une séquence, comme une liste, un ensemble ou une plage de nombres.

### Syntaxe

```python
for element in sequence:
    # bloc de code à exécuter
```

### Exemple 1 : Parcourir une liste
```python
animaux = ["chat", "chien", "oiseau"]
for animal in animaux:
    print(animal)
```

### Exemple 2 : Utiliser `range` pour générer des nombres
```python
for nombre in range(1, 6):  # Nombres de 1 à 5
    print(nombre)
```

### Utilisation avancée de `range`
- `range(stop)` : Génère des nombres de `0` à `stop - 1`.
- `range(start, stop)` : Génère des nombres de `start` à `stop - 1`.
- `range(start, stop, step)` : Génère des nombres de `start` à `stop - 1`, avec un pas de `step`.

#### Exemple : Afficher les nombres pairs
```python
for nombre in range(0, 11, 2):
    print(nombre)
```

---

## 3. Boucles imbriquées

Les boucles imbriquées permettent de parcourir des structures complexes, comme des tableaux à deux dimensions, ou de générer des motifs.

### Exemple 1 : Carré de caractères
```python
taille = 4
for i in range(taille):
    for j in range(taille):
        print("#", end="")
    print()  # Nouvelle ligne après chaque ligne complète
```

### Exemple 2 : Triangle de caractères
```python
hauteur = 4
for i in range(hauteur):
    for j in range(i + 1):
        print("*", end="")
    print()
```

---

## 4. Conseils et bonnes pratiques

### Quand utiliser une boucle `for` ?
Utilisez une boucle `for` lorsque le nombre d’itérations est connu à l’avance.

### Modifications de séquence
Ne modifiez pas directement une séquence sur laquelle vous itérez ; cela peut entraîner des erreurs. Copiez la séquence si nécessaire :

```python
nombres = [1, 2, 3, 4]
for nombre in nombres[:]:  # Utilisation d'une copie
    if nombre % 2 == 0:
        nombres.remove(nombre)
print(nombres)  # Résultat : [1, 3]
```

### Améliorer la lisibilité
Lorsque les boucles imbriquées deviennent complexes, envisagez d’utiliser des fonctions pour clarifier votre code.

#### Exemple : Fonction pour un motif personnalisé
```python
def imprimer_ligne(taille):
    for _ in range(taille):
        print("*", end="")
    print()

hauteur = 5
for i in range(hauteur):
    imprimer_ligne(i + 1)
```

---

## Conclusion

Les structures itératives, `while` et `for`, sont des outils puissants pour automatiser des tâches répétitives. En comprenant leurs comportements et leurs limites, vous pourrez écrire du code Python plus efficace et lisible.

---

### Ressources supplémentaires
- [Documentation Python sur les boucles](https://docs.python.org/3/tutorial/controlflow.html#for-statements)

