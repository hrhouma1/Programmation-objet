# **Examen 2 : Classes Abstraites, Polymorphisme, Décorateurs, Getters et Setters**

**Objectif :** Cet examen vous guidera **progressivement** dans l’utilisation de la **programmation orientée objet avancée** en Python, en mettant l'accent sur les **classes abstraites**, le **polymorphisme**, les **décorateurs**, et les **getters/setters avec validation**.

**Règle :** Vous devez **réécrire le code complet** pour chaque question en suivant les instructions et les pseudo-codes fournis.

---

## **Partie 1 : Création d'une classe abstraite**

### **Question 1 : Définition d'une classe `Animal` abstraite**

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

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def parler(self):
        pass
```

```
+---------------+
|    Animal     |
+---------------+
| + parler()    |  <-- Abstraite
+---------------+
```

---

## **Partie 2 : Classe concrète héritée**

### **Question 2 : Création de la classe `Chien`**

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

```python
class Chien(Animal):
    def parler(self):
        print("Le chien aboie.")
```

```
+--------------+
|    Chien     |
+--------------+
| + parler()   |
+--------------+
```

---

## **Partie 3 : Polymorphisme**

### **Question 3 : Ajouter une classe `Chat` et illustrer le polymorphisme**

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

```python
class Chat(Animal):
    def parler(self):
        print("Le chat miaule.")

animaux = [Chien(), Chat()]

for animal in animaux:
    animal.parler()
```

📌 **💡 Output attendu :**
```
Le chien aboie.
Le chat miaule.
```

```
+---------------+
|   Animal      |
+---------------+
| + parler()    |
+---------------+
       ▲
       │
+------+--------+ 
|               |
|  Chien       Chat 
| + parler()   + parler() 
+---------------+ 
```

---

## **Partie 4 : Décorateur `logger`**

### **Question 4 : Création d'un décorateur pour tracer les appels de méthode**

```plaintext
Définir un décorateur logger  
L’appliquer à parler()  
Afficher "Appel de la méthode : <nom>"  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```python
def logger(fonction):
    def wrapper(*args, **kwargs):
        print(f"Appel de la méthode : {fonction.__name__}")
        return fonction(*args, **kwargs)
    return wrapper

class Chien(Animal):
    @logger
    def parler(self):
        print("Le chien aboie.")

c = Chien()
c.parler()
```

📌 **💡 Output attendu :**
```
Appel de la méthode : parler  
Le chien aboie.
```

```
+--------------+
|    Chien     |
+--------------+
| + parler()   |  <-- décorée avec logger
+--------------+
```

---

## **Partie 5 : Getters et Setters avec `@property`**

### **Question 5 : Encapsulation avec validation**

```plaintext
Créer la classe Voiture avec __kilometrage  
Créer un getter avec @property  
Créer un setter avec validation (≥ 0)  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```python
class Voiture:
    def __init__(self, marque, kilometrage):
        self.marque = marque
        self.__kilometrage = kilometrage

    @property
    def kilometrage(self):
        return self.__kilometrage

    @kilometrage.setter
    def kilometrage(self, valeur):
        if valeur < 0:
            raise ValueError("Le kilométrage ne peut pas être négatif.")
        self.__kilometrage = valeur
```

```python
v = Voiture("Toyota", 10000)
print("Kilométrage :", v.kilometrage)  # 10000
v.kilometrage = 20000
print("Nouveau kilométrage :", v.kilometrage)
```

```
+----------------+
|   Voiture      |
+----------------+
| - __kilometrage |
+----------------+
| + kilometrage() |
| + kilometrage=()| <-- setter avec validation
+----------------+
```



---

## **Partie 6 : Tester la modification et la validation**

### **Question 6 : Utilisation du setter avec une valeur invalide**

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

```python
class Voiture:
    def __init__(self, marque, kilometrage):
        self.marque = marque
        self.__kilometrage = kilometrage

    @property
    def kilometrage(self):
        return self.__kilometrage

    @kilometrage.setter
    def kilometrage(self, valeur):
        if valeur < 0:
            raise ValueError("Le kilométrage ne peut pas être négatif.")
        self.__kilometrage = valeur

v = Voiture("Toyota", 10000)
print("Kilométrage actuel :", v.kilometrage)
v.kilometrage = 40000
print("Nouveau kilométrage :", v.kilometrage)

try:
    v.kilometrage = -10
except ValueError as e:
    print("Erreur :", e)
```

📌 **💡 Output attendu :**
```
Kilométrage actuel : 10000  
Nouveau kilométrage : 40000  
Erreur : Le kilométrage ne peut pas être négatif.
```

---

## **Partie 7 : Décorateur appliqué au setter**

### **Question 7 : Utiliser un décorateur `verifier_valeur_positive`**

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

```python
def verifier_valeur_positive(setter_fonction):
    def wrapper(self, valeur):
        if valeur < 0:
            raise ValueError("Valeur négative non autorisée.")
        setter_fonction(self, valeur)
    return wrapper

class Voiture:
    def __init__(self, marque, kilometrage):
        self.marque = marque
        self.__kilometrage = kilometrage

    @property
    def kilometrage(self):
        return self.__kilometrage

    @kilometrage.setter
    @verifier_valeur_positive
    def kilometrage(self, valeur):
        self.__kilometrage = valeur

v = Voiture("BMW", 8000)
v.kilometrage = 20000
print(v.kilometrage)

try:
    v.kilometrage = -100
except ValueError as e:
    print("Erreur :", e)
```

📌 **💡 Output attendu :**
```
20000  
Erreur : Valeur négative non autorisée.
```

---

## **Partie 8 : Classe abstraite avec méthode concrète**

### **Question 8 : Ajouter une méthode utilitaire non abstraite**

```plaintext
Créer une classe Personne avec parler() abstrait  
Ajouter une méthode presentation() concrète  
Créer deux classes concrètes (Professeur, Étudiant)  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```python
from abc import ABC, abstractmethod

class Personne(ABC):
    @abstractmethod
    def parler(self):
        pass

    def presentation(self):
        print("Je suis une personne.")

class Professeur(Personne):
    def parler(self):
        print("Bonjour, je suis votre professeur.")

class Etudiant(Personne):
    def parler(self):
        print("Salut, je suis étudiant.")

p = Professeur()
e = Etudiant()

p.presentation()
p.parler()

e.presentation()
e.parler()
```

📌 **💡 Output attendu :**
```
Je suis une personne.  
Bonjour, je suis votre professeur.  
Je suis une personne.  
Salut, je suis étudiant.
```

```
+------------------+
|    Personne      |
+------------------+
| + parler()       | <-- Abstraite
| + presentation() |
+------------------+
       ▲
   +---+----+
   |        |
Professeur  Etudiant
+ parler()  + parler()
```

---

## **Partie 9 : Surcharge de `__str__()` et polymorphisme**

### **Question 9 : Affichage personnalisé par classe**

```plaintext
Créer classes Professeur et Étudiant  
Surcharger __str__() dans chaque classe  
Afficher une liste de personnes  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```python
class Professeur(Personne):
    def __init__(self, nom):
        self.nom = nom

    def parler(self):
        print("Je donne cours.")

    def __str__(self):
        return f"Professeur : {self.nom}"

class Etudiant(Personne):
    def __init__(self, nom):
        self.nom = nom

    def parler(self):
        print("Je suis en cours.")

    def __str__(self):
        return f"Étudiant : {self.nom}"

personnes = [Professeur("Jean Dupont"), Etudiant("Alice Martin")]

for p in personnes:
    print(p)
```

📌 **💡 Output attendu :**
```
Professeur : Jean Dupont  
Étudiant : Alice Martin
```

---

## **Partie 10 : Mini-projet final (tout combiné)**

### **Question 10 : Mise en œuvre complète**

```plaintext
Créer une classe abstraite Animal avec parler()  
Créer Chien et Chat  
Ajouter un décorateur sur parler()  
Ajouter un attribut privé age avec getter/setter validé  
Afficher les infos  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```python
from abc import ABC, abstractmethod

def logger(f):
    def wrapper(*args, **kwargs):
        print(f"Appel de la méthode : {f.__name__}")
        return f(*args, **kwargs)
    return wrapper

class Animal(ABC):
    def __init__(self, age):
        self.__age = age

    @abstractmethod
    def parler(self):
        pass

    @property
    def age(self):
        return self.__age

    @age.setter
    def age(self, valeur):
        if valeur < 0:
            raise ValueError("L'âge doit être positif.")
        self.__age = valeur

class Chien(Animal):
    @logger
    def parler(self):
        print(f"Le chien aboie. Il a {self.age} ans.")

class Chat(Animal):
    def parler(self):
        print(f"Le chat miaule. Il a {self.age} ans.")

c = Chien(5)
ch = Chat(3)

c.parler()
ch.parler()
```

📌 **💡 Output attendu :**
```
Appel de la méthode : parler  
Le chien aboie. Il a 5 ans.  
Le chat miaule. Il a 3 ans.
```

```
+-------------+
|   Animal    |
+-------------+
| - __age     |
+-------------+
| + age       |
| + age=      |
| + parler()  |
+-------------+
       ▲
   +---+----+
   |        |
Chien      Chat
+ parler() + parler()
(décoré)    
```
