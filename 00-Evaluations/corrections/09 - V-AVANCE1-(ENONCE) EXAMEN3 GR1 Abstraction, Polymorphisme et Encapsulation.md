# **Examen 2 : Abstraction, Polymorphisme et Encapsulation avancée en Python**

**Objectif :** Cet examen vous guidera **progressivement** à travers des concepts avancés de la Programmation Orientée Objet en Python, incluant les **classes abstraites**, **le polymorphisme**, **les décorateurs**, **les getters et setters**.

**Règle :** Vous devez **réécrire le code complet** pour chaque question en suivant les instructions et les pseudo-codes fournis.

---

## **Partie 1 : Création d'une classe abstraite**

### **Question 1 : Définition d'une classe `Animal` abstraite**

Utilisez le module `abc` pour créer une **classe abstraite `Animal`** avec une méthode abstraite `parler()`.

```plaintext
Importer ABC, abstractmethod  
Créer une classe Animal héritant de ABC  
Définir une méthode abstraite parler()  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

## **Partie 2 : Implémentation concrète d'une classe**

### **Question 2 : Création de la classe `Chien`**

Créez une classe `Chien` qui hérite de `Animal` et implémente la méthode `parler()`.

```plaintext
Créer une classe Chien(Animal)  
Implémenter parler() avec "Le chien aboie."  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

## **Partie 3 : Polymorphisme**

### **Question 3 : Utilisation polymorphe de plusieurs classes**

Créez une autre classe `Chat` héritant d'`Animal`, et utilisez une boucle pour appeler `parler()` sur plusieurs objets.

```plaintext
Créer une classe Chat(Animal), implémenter parler()  
Créer une liste contenant un Chien et un Chat  
Boucler sur la liste et appeler parler()  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**
```
Le chien aboie.
Le chat miaule.
```

---

## **Partie 4 : Décorateurs – Logger**

### **Question 4 : Création d'un décorateur `logger`**

Créez un décorateur `logger` qui affiche un message avant d’exécuter une méthode.

```plaintext
Définir un décorateur logger  
L’appliquer à une méthode quelconque (ex. parler())  
Afficher "Appel de la méthode : <nom>"  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**
```
Appel de la méthode : parler
Le chien aboie.
```

---

## **Partie 5 : Getters et Setters avec `@property`**

### **Question 5 : Encapsulation avec `@property`**

Créez une classe `Voiture` avec un attribut privé `__kilometrage`, un getter, un setter, et des règles de validation.

```plaintext
Créer la classe Voiture avec __kilometrage  
Utiliser @property pour créer un getter  
Utiliser @<attribut>.setter pour créer un setter  
Valider que le kilométrage est ≥ 0  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

## **Partie 6 : Application des setters dans un scénario**

### **Question 6 : Tester la modification du kilométrage**

Créez un objet `Voiture`, essayez d'afficher et de modifier le kilométrage. Testez avec une valeur invalide.

```plaintext
Créer une instance  
Afficher le kilométrage  
Modifier le kilométrage à 40000  
Essayer de le modifier à -10 et afficher une erreur  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**
```
Kilométrage actuel : 10000
Nouveau kilométrage : 40000
Erreur : Le kilométrage ne peut pas être négatif.
```

---

## **Partie 7 : Décorateur pour valider un setter**

### **Question 7 : Ajouter un décorateur `verifier_valeur_positive`**

Utilisez un décorateur pour **valider automatiquement** une valeur passée à une méthode (ex : setter de kilométrage).

```plaintext
Créer un décorateur verifier_valeur_positive  
L’utiliser sur le setter de kilometrage  
Lever une exception si la valeur est négative  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

## **Partie 8 : Classe abstraite avec méthode concrète**

### **Question 8 : Classe `Personne` avec une méthode abstraite et une méthode utilitaire**

Créer une classe `Personne` abstraite avec `parler()` abstrait et une méthode concrète `presentation()`.

```plaintext
Créer une classe Personne avec ABC  
Ajouter une méthode parler() abstraite  
Ajouter une méthode presentation() qui affiche "Je suis une personne."  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

## **Partie 9 : Surcharge de méthode `__str__` et polymorphisme**

### **Question 9 : Personnalisation de l’affichage avec `__str__`**

Créer plusieurs classes dérivées de `Personne` et personnaliser l'affichage avec `__str__()`.

```plaintext
Créer classes Professeur et Étudiant  
Surcharger __str__() pour afficher des infos différentes  
Créer une liste de Personne, afficher chaque élément  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**
```
Professeur : Jean Dupont
Étudiant : Alice Martin
```

---

## **Partie 10 : Récapitulatif – Mise en œuvre complète**

### **Question 10 : Combinaison de tous les concepts**

Créez un mini-système avec :

- une classe abstraite
- deux classes filles
- une méthode décorée
- des getters et setters avec validation
- et l’utilisation du polymorphisme

```plaintext
Créer Animal (abstraite), Chien et Chat  
Ajouter @property et setter sur l’âge avec validation  
Décorer une méthode de `Chien` avec logger  
Créer des objets, les manipuler, et afficher leur état  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**
```
Appel de la méthode : parler
Le chien aboie. Il a 5 ans.
Le chat miaule. Il a 3 ans.
```

