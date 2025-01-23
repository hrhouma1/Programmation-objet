# Les fonctions en Python

## Introduction

Les fonctions sont des blocs de code organisés qui permettent d'exécuter des tâches spécifiques. Elles rendent le code plus lisible, réutilisable et facile à maintenir. Une bonne maîtrise des fonctions est essentielle pour structurer vos programmes efficacement.

---

## 1. Utilité des fonctions

Les fonctions permettent de :
- **Éviter la duplication de code** : Le même bloc de code peut être appelé plusieurs fois.
- **Améliorer la lisibilité** : Chaque fonction a une tâche spécifique.
- **Faciliter la maintenance** : Modifier une fonction met à jour son comportement partout où elle est utilisée.

---

## 2. Définir une fonction

### Exemple : Fonction sans paramètres
```python
def saluer():
    print("Bonjour !")

saluer()  # Affiche "Bonjour !"
```

### Exemple : Fonction avec paramètres
```python
def additionner(a, b):
    return a + b

resultat = additionner(5, 7)
print(resultat)  # Affiche 12
```

---

## 3. Valeurs par défaut pour les paramètres

Si un paramètre a une valeur par défaut, il devient optionnel lors de l'appel.

```python
def saluer(nom="ami"):
    print(f"Bonjour, {nom} !")

saluer()  # Affiche "Bonjour, ami !"
saluer("Alice")  # Affiche "Bonjour, Alice !"
```

---

## 4. Retourner plusieurs valeurs

Les fonctions peuvent retourner plusieurs valeurs sous forme de tuple.

```python
def calculer(valeur):
    carre = valeur ** 2
    cube = valeur ** 3
    return carre, cube

carre, cube = calculer(3)
print(f"Carré : {carre}, Cube : {cube}")  # Affiche "Carré : 9, Cube : 27"
```

---

## 5. Arguments variables avec `*args`

Utilisez `*args` pour accepter un nombre variable d'arguments.

```python
def additionner_tout(*nombres):
    return sum(nombres)

print(additionner_tout(1, 2, 3))  # Affiche 6
print(additionner_tout(5, 10))  # Affiche 15
```

---

## 6. Portée des variables

### Variables locales
Les variables définies dans une fonction sont locales et ne sont pas accessibles à l'extérieur.

```python
def exemple():
    x = 10
    print(x)  # Affiche 10

exemple()
# print(x)  # Erreur : x n'est pas défini en dehors de la fonction
```

### Variables globales
Les variables définies en dehors d'une fonction sont globales. Pour les modifier dans une fonction, utilisez le mot-clé `global`.

```python
x = 5  # Variable globale

def changer_x():
    global x
    x = 10

changer_x()
print(x)  # Affiche 10
```

---

## 7. Appeler une fonction depuis une autre fonction

Les fonctions peuvent être combinées pour diviser une tâche complexe en sous-tâches.

```python
def chauffer_eau(temperature):
    return f"Eau chauffée à {temperature}°C"

def faire_du_the():
    eau = chauffer_eau(100)
    print(f"Préparer le thé avec {eau}.")

faire_du_the()
# Affiche "Préparer le thé avec Eau chauffée à 100°C."
```

---

## 8. Bonnes pratiques avec les fonctions

### Utilisation d'objets mutables
Les objets comme les listes ou dictionnaires doivent être manipulés avec précaution lorsqu'ils sont utilisés comme valeurs par défaut.

```python
def ajouter_element(element, liste=None):
    if liste is None:
        liste = []
    liste.append(element)
    return liste

print(ajouter_element(1))  # Affiche [1]
print(ajouter_element(2))  # Affiche [2]
```

---

## 9. Appels par mot-clé

Les arguments peuvent être passés dans un ordre différent en utilisant leurs noms.

```python
def decrire_personne(nom, age, ville):
    print(f"{nom} a {age} ans et habite à {ville}.")

decrire_personne(age=25, ville="Lyon", nom="Paul")
# Affiche "Paul a 25 ans et habite à Lyon."
```

---

## 10. Paramètres avec **kwargs

Pour gérer des arguments nommés dynamiques, utilisez `**kwargs`.

```python
def afficher_infos(**infos):
    for cle, valeur in infos.items():
        print(f"{cle} : {valeur}")

afficher_infos(nom="Marie", age=28, ville="Paris")
# Affiche :
# nom : Marie
# age : 28
# ville : Paris
```

---

## Conclusion

Les fonctions sont un pilier essentiel de la programmation en Python. En les utilisant correctement, vous pouvez rendre vos programmes plus efficaces, lisibles et modulaires.

---

## Ressources supplémentaires
- [Documentation officielle sur les fonctions Python](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)

