---
title: "Pratique 2 - Héritage en Python avec une Application de Gestion d'Animaux"
description: "Un exercice complet et progressif sur l'héritage en Python, illustré avec une application de gestion d'animaux. Ce cours vous guide étape par étape pour créer des classes parentes et filles, utiliser super(), et appliquer la surcharge de méthodes."
emoji: "🐾"
tags: ["python2", "oop", "inheritance", "pratique"]
sidebar_position: 3
slug: "/docs/python2/week4/pratique_heritage"
---

# **Pratique 2 - Héritage en Python avec une Application de Gestion d'Animaux**  
*Un guide pas-à-pas pour maîtriser l'héritage en Python et créer une application complète de gestion d'animaux.*  

---
<a name="table-des-matieres"></a>  

## **Table des Matières**  
1. [Introduction](#introduction)  
2. [Création de la classe parente `Animal`](#classe-parente-animal)  
3. [Ajout de classes filles `Chien` et `Chat`](#classes-filles-chien-chat)  
4. [Utilisation de `super()` pour éviter la répétition](#utilisation-de-super)  
5. [Surcharge de méthodes dans les classes filles](#surcharge-de-methodes)  
6. [Ajout d'une méthode commune et polymorphisme](#methode-commune-et-polymorphisme)  
7. [Interaction avec l'utilisateur : Ajouter des animaux via la console](#interaction-avec-utilisateur)  
8. [Test complet de l'application](#test-complet)  
9. [Résumé et bonnes pratiques](#resume-et-bonnes-pratiques)  



<a id="introduction"></a>  
<br/>


## 1. Introduction  

L'héritage en Python est un concept puissant qui permet de créer de nouvelles classes en réutilisant du code existant. Dans cette pratique, nous allons construire une **application de gestion d'animaux** en utilisant l'héritage, tout en ajoutant des fonctionnalités comme l'interaction via la console, l'affichage des informations, et des méthodes spécifiques à chaque type d'animal.


<a id="classe-parente-animal"></a>  
<br/>
---
## 2. Création de la classe parente `Animal`  
---

La classe parente `Animal` contiendra les attributs et méthodes de base que tous les animaux partagent.  

```python
class Animal:
    def __init__(self, nom, age, espece):
        self.nom = nom
        self.age = age
        self.espece = espece

    def afficher_info(self):
        print(f"Nom: {self.nom}, Âge: {self.age} ans, Espèce: {self.espece}")
```

**Explication :**  
- `__init__` initialise `nom`, `age` et `espece`.  
- `afficher_info` est une méthode commune qui affiche les informations de l'animal.  

[🔙 Retour à la table des matières](#table-des-matieres)  



<a id="classes-filles-chien-chat"></a>  
<br/>

---
## 3. Ajout de classes filles `Chien` et `Chat`  
---

Créons deux classes filles, `Chien` et `Chat`, qui hériteront de `Animal`.  

```python
class Chien(Animal):
    def __init__(self, nom, age, race):
        super().__init__(nom, age, "Chien")
        self.race = race

class Chat(Animal):
    def __init__(self, nom, age, couleur):
        super().__init__(nom, age, "Chat")
        self.couleur = couleur
```

**Ce qu'il faut retenir :**  
- `Chien` et `Chat` utilisent `super()` pour appeler le constructeur de `Animal`.  
- Chaque classe ajoute un attribut spécifique : `race` pour `Chien` et `couleur` pour `Chat`.  

[🔙 Retour à la table des matières](#table-des-matieres)  

<a id="utilisation-de-super"></a>  
<br/>
---
## 4. Utilisation de `super()` pour éviter la répétition  
---

Pourquoi `super()` est important ?  
- Il évite de répéter l'initialisation des attributs communs (`nom`, `age`, `espece`).  
- Il garantit que le code est **réutilisable** et **facile à maintenir**.  

**Exemple sans `super()` :**  
```python
self.nom = nom
self.age = age
self.espece = "Chien"
```
Cette approche oblige à répéter le code pour chaque classe fille.  

**Avec `super()` :**  
```python
super().__init__(nom, age, "Chien")
```
Cette ligne appelle directement le constructeur de `Animal` et initialise les attributs.  

[🔙 Retour à la table des matières](#table-des-matieres)  


<a id="surcharge-de-methodes"></a>  
<br/>
---
## 5. Surcharge de méthodes dans les classes filles  
---

La surcharge permet de redéfinir une méthode existante dans la classe parente.  

**Ajoutons une méthode `faire_du_bruit()` dans `Animal`, et surchargeons-la dans `Chien` et `Chat` :**  

```python
class Animal:
    def __init__(self, nom, age, espece):
        self.nom = nom
        self.age = age
        self.espece = espece

    def afficher_info(self):
        print(f"Nom: {self.nom}, Âge: {self.age} ans, Espèce: {self.espece}")

    def faire_du_bruit(self):
        print("L'animal fait un bruit.")
        
class Chien(Animal):
    def __init__(self, nom, age, race):
        super().__init__(nom, age, "Chien")
        self.race = race

    def faire_du_bruit(self):
        print("Le chien aboie !")
        
class Chat(Animal):
    def __init__(self, nom, age, couleur):
        super().__init__(nom, age, "Chat")
        self.couleur = couleur

    def faire_du_bruit(self):
        print("Le chat miaule !")
```

**Pourquoi c'est utile ?**  
Chaque classe fille peut **avoir son propre comportement** tout en partageant la même structure.  

[🔙 Retour à la table des matières](#table-des-matieres)  


<a id="methode-commune-et-polymorphisme"></a>  
<br/>

---
## 6. Ajout d'une méthode commune et polymorphisme  
---

Le polymorphisme permet d'utiliser des objets de différentes classes de manière interchangeable.  

**Ajoutons une méthode `se_deplacer()` à `Animal` et modifions-la dans les classes filles :**  

```python
class Animal:
    def se_deplacer(self):
        print("L'animal se déplace.")

class Chien(Animal):
    def se_deplacer(self):
        print("Le chien court.")

class Chat(Animal):
    def se_deplacer(self):
        print("Le chat saute.")
```

Maintenant, **tous les animaux partagent la même interface**, mais chaque classe fille peut définir son propre comportement.  

[🔙 Retour à la table des matières](#table-des-matieres)  

<a id="interaction-avec-utilisateur"></a>  
<br/>

---
## 7. Interaction avec l'utilisateur : Ajouter des animaux via la console  
---

Intégrons un **menu interactif** pour ajouter des animaux et afficher leurs détails :  

```python
animaux = []

while True:
    choix = input("Voulez-vous ajouter un chien (c), un chat (h), ou quitter (q) ? ")

    if choix == 'q':
        break
    elif choix == 'c':
        nom = input("Nom du chien : ")
        age = int(input("Âge du chien : "))
        race = input("Race du chien : ")
        animaux.append(Chien(nom, age, race))
    elif choix == 'h':
        nom = input("Nom du chat : ")
        age = int(input("Âge du chat : "))
        couleur = input("Couleur du chat : ")
        animaux.append(Chat(nom, age, couleur))
    else:
        print("Choix invalide, réessayez.")

print("\n--- Liste des animaux ---")
for animal in animaux:
    animal.afficher_info()
    animal.faire_du_bruit()
    animal.se_deplacer()
```

[🔙 Retour à la table des matières](#table-des-matieres)  



<a id="test-complet"></a>  
<br/>

---
## 8. Test complet de l'application  
---

**Lancez le code** et ajoutez plusieurs animaux pour tester :  
- L'affichage correct des informations.  
- L'utilisation de `super()` pour éviter les répétitions.  
- La surcharge de méthodes pour personnaliser les actions de chaque animal.  

[🔙 Retour à la table des matières](#table-des-matieres)  


<a id="resume-et-bonnes-pratiques"></a>  
<br/>
---
## 9. Résumé et bonnes pratiques  
---

- **Héritage** : Permet de créer de nouvelles classes en réutilisant du code existant.  
- **`super()`** : Appelle la classe parente et évite la répétition.  
- **Surcharge** : Modifie une méthode héritée dans la classe fille.  
- **Polymorphisme** : Permet d'utiliser des classes filles de manière uniforme.  

**Bonnes pratiques :**  
- Utilisez des noms explicites pour vos classes et méthodes.  
- Appliquez `super()` systématiquement dans vos classes filles.  
- Testez régulièrement vos classes avec des exemples concrets.  

Bravo ! 🎉 Vous avez créé une application complète en utilisant l'héritage en Python ! Continuez à pratiquer et à explorer. 🚀  

[🔙 Retour à la table des matières](#table-des-matieres)  
