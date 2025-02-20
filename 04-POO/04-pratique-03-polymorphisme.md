---
title: "Pratique 3 - Héritage et Polymorphisme en Python - Application de Gestion de Zoo"
description: "Une application complète illustrant l'héritage et le polymorphisme en Python, avec des étapes détaillées, des exemples enrichis et des instructions pédagogiques."
slug: "/docs/python2/week4/pratique_polymorphisme"
emoji: "🦁"
---

# Pratique 3 - Héritage et Polymorphisme en Python - Application de Gestion de Zoo

*Dans cette pratique, nous allons construire étape par étape une application Python de gestion de zoo, en illustrant l'héritage, la surcharge de méthodes et le polymorphisme, avec des explications claires et des exemples riches.*
<a name="table-des-matieres"></a>  

---

## Table des Matières

1. [Introduction à l'héritage et au polymorphisme](#partie-1)
2. [Créer la classe parente `Animal`](#partie-2)
3. [Créer les classes filles `Mammifere`, `Oiseau` et `Reptile`](#partie-3)
4. [Ajouter des méthodes spécifiques et surcharger des méthodes](#partie-4)
5. [Démontrer le polymorphisme avec une fonction commune](#partie-5)
6. [Créer des instances et tester l'application](#partie-6)
7. [Résumé et bonnes pratiques](#partie-7)

<a name="partie-1"></a>  
<br/>
---
## 1. Introduction à l'héritage et au polymorphisme  
---

L'héritage permet de **réutiliser du code** en partageant les attributs et méthodes entre une classe parente et ses classes filles.  
Le polymorphisme permet d'utiliser une même méthode avec des comportements différents selon l'objet qui l'appelle.  

### **Notre projet :**  
Nous allons créer une application pour gérer les animaux d'un zoo, en utilisant :  
- Une classe **parente** `Animal` pour représenter les propriétés et méthodes communes à tous les animaux.
- Des classes **filles** `Mammifere`, `Oiseau` et `Reptile` qui hériteront de `Animal` et ajouteront leurs spécificités.
- Une fonction `faire_crier_animal` qui illustrera le polymorphisme.

[🔙 Retour à la table des matières](#table-des-matieres)  
<a name="partie-2"></a>  
<br/>

---
## 2. Créer la classe parente `Animal`  
---

```python
class Animal:
    def __init__(self, nom, age, habitat):
        self.nom = nom
        self.age = age
        self.habitat = habitat

    def afficher_details(self):
        print(f"{self.nom}, {self.age} ans, Habitat: {self.habitat}")

    def crier(self):
        print("L'animal fait un bruit.")
```

🔹 **Explication :**  
- `__init__` initialise les attributs communs à tous les animaux.
- `afficher_details` affiche les informations d'un animal.
- `crier` est une méthode générale qui sera **surchargée** dans les classes filles.



[🔙 Retour à la table des matières](#table-des-matieres)  
<a name="partie-3"></a>  
<br/>
---
## 3. Créer les classes filles `Mammifere`, `Oiseau` et `Reptile`  
---

```python
class Mammifere(Animal):
    def __init__(self, nom, age, habitat, type_poils):
        super().__init__(nom, age, habitat)
        self.type_poils = type_poils

class Oiseau(Animal):
    def __init__(self, nom, age, habitat, envergure):
        super().__init__(nom, age, habitat)
        self.envergure = envergure

class Reptile(Animal):
    def __init__(self, nom, age, habitat, type_peau):
        super().__init__(nom, age, habitat)
        self.type_peau = type_peau
```

🔹 **Explication :**  
- `super().__init__` appelle le constructeur de `Animal` pour éviter de répéter du code.
- Chaque classe fille ajoute un attribut spécifique :
  - `Mammifere` : type de poils,
  - `Oiseau` : envergure,
  - `Reptile` : type de peau.


[🔙 Retour à la table des matières](#table-des-matieres)  
<a name="partie-4"></a>  
<br/>

---
## 4. Ajouter des méthodes spécifiques et surcharger des méthodes  
---

```python
class Mammifere(Animal):
    def __init__(self, nom, age, habitat, type_poils):
        super().__init__(nom, age, habitat)
        self.type_poils = type_poils

    def crier(self):
        print(f"{self.nom} rugit comme un mammifère !")

class Oiseau(Animal):
    def __init__(self, nom, age, habitat, envergure):
        super().__init__(nom, age, habitat)
        self.envergure = envergure

    def crier(self):
        print(f"{self.nom} chante comme un oiseau !")

class Reptile(Animal):
    def __init__(self, nom, age, habitat, type_peau):
        super().__init__(nom, age, habitat)
        self.type_peau = type_peau

    def crier(self):
        print(f"{self.nom} siffle comme un reptile !")
```

🔹 **Explication :**  
- Chaque classe **surcharge** la méthode `crier` pour afficher un son spécifique.
- `super()` évite de réécrire les attributs communs.



[🔙 Retour à la table des matières](#table-des-matieres)  
<a name="partie-5"></a>  
<br/>

---
## 5. Démontrer le polymorphisme avec une fonction commune  
---

```python
def faire_crier_animal(animal):
    animal.crier()
```

🔹 **Explication :**  
- La fonction `faire_crier_animal` est **polymorphe** : elle appelle la méthode `crier` sur n'importe quel objet `Animal` ou dérivé.

[🔙 Retour à la table des matières](#table-des-matieres)  
<a name="partie-6"></a>  
<br/>

---
## 6. Créer des instances et tester l'application  
---

```python
m1 = Mammifere("Lion", 5, "Savane", "Crinière")
o1 = Oiseau("Aigle", 3, "Montagne", "2 mètres")
r1 = Reptile("Python", 8, "Forêt", "Écailles")

zoo = [m1, o1, r1]

for animal in zoo:
    animal.afficher_details()
    faire_crier_animal(animal)
    print("-" * 30)
```

🔹 **Explication :**  
- Nous créons des instances de chaque classe fille.
- Nous utilisons la fonction polymorphe `faire_crier_animal` pour montrer comment chaque objet utilise sa propre version de `crier`.

[🔙 Retour à la table des matières](#table-des-matieres)  
<a name="partie-7"></a>  
<br/>

---
## 7. Résumé et bonnes pratiques  
---

- **L'héritage** évite la duplication de code et rend le programme plus lisible.
- **La surcharge de méthodes** permet de personnaliser le comportement des classes filles.
- **Le polymorphisme** rend le code flexible et réutilisable.
- **Utilisez `super()`** pour simplifier et éviter les erreurs dans l'héritage.

---

🎉 **Félicitations !** Vous avez créé une application complète de gestion de zoo, illustrant l'héritage, la surcharge de méthodes et le polymorphisme en Python !

[🔙 Retour à la table des matières](#table-des-matieres)  
<a name="partie-7"></a>  
<br/>