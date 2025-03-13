## **Examen 1 : Concepts avancés de la Programmation Orientée Objet en Python**  

**Objectif :** Cet examen vous guidera **progressivement** à travers la création d'une classe et son enrichissement avec des **attributs, méthodes, héritage, utilisation de `super()`, héritage multiple, et vérifications de types** en Python.  

**Règle :** Vous devez **réécrire le code complet** pour chaque question en suivant les instructions et les pseudo-codes fournis.  

---

## **Partie 1 : Création d'une classe vide**  

### **Question 1 : Définition d'une classe `Voiture`**  
Définissez une classe `Voiture` en Python, sans rien ajouter à l'intérieur.  

```plaintext
Définir une classe Voiture  
Ajouter une instruction minimale pour éviter une erreur  
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
    pass
```

```
+-----------------+
|    Voiture     |
+-----------------+
|                |
+-----------------+
```

---

## **Partie 2 : Ajout des attributs d'instance**  

### **Question 2 : Définition des attributs `marque` et `couleur`**  
Ajoutez les **attributs d’instance** `marque` et `couleur` à la classe `Voiture`, **sans constructeur**.  

```plaintext
Déclarer les attributs d’instance marque et couleur sans constructeur  
Créer un objet v1 de Voiture  
Assigner une marque et une couleur  
Afficher ces valeurs  
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
    pass

# Création d'un objet
v1 = Voiture()

# Ajout des attributs d'instance
v1.marque = "Toyota"
v1.couleur = "Bleu"

# Affichage des attributs
print(v1.marque)  # Toyota
print(v1.couleur)  # Bleu
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
+-----------------+
```

---

## **Partie 3 : Ajout d'un constructeur (`__init__`)**  

### **Question 3 : Ajout du constructeur `__init__`**  
Ajoutez un **constructeur (`__init__`)** qui prend en paramètres `marque` et `couleur`, et stocke ces valeurs dans les attributs correspondants.  

```plaintext
Définir une méthode __init__(self, marque, couleur)  
Initialiser les attributs d'instance marque et couleur  
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
    def __init__(self, marque, couleur):
        self.marque = marque
        self.couleur = couleur
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
+-----------------+
| + __init__()   |
+-----------------+
```

---

## **Partie 4 : Ajout d'une méthode d'instance**  

### **Question 4 : Ajout de la méthode `decrire()`**  
Ajoutez une **méthode `decrire()`** qui retourne une phrase décrivant la voiture.  

```plaintext
Définir une méthode decrire(self)  
Retourner une chaîne contenant marque et couleur  
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
    def __init__(self, marque, couleur):
        self.marque = marque
        self.couleur = couleur

    def decrire(self):
        return f"Cette voiture est une {self.marque} de couleur {self.couleur}."
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
+-----------------+
| + __init__()   |
| + decrire()    |
+-----------------+
```

---

## **Partie 5 : Ajout d’un attribut de classe**  

### **Question 5 : Ajout de l’attribut `nombre_roues`**  
Ajoutez un **attribut de classe** `nombre_roues` (qui vaut `4` pour toutes les voitures).  

```plaintext
Déclarer un attribut de classe nombre_roues avec la valeur 4  
Modifier `decrire()` pour inclure nombre_roues  
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
    nombre_roues = 4  # Attribut de classe

    def __init__(self, marque, couleur):
        self.marque = marque
        self.couleur = couleur

    def decrire(self):
        return f"Cette voiture est une {self.marque} de couleur {self.couleur} avec {Voiture.nombre_roues} roues."
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - nombre_roues |  <-- Attribut de classe
+-----------------+
| + __init__()   |
| + decrire()    |
+-----------------+
```

---

## **Partie 6 : Ajout d'une méthode de classe**  

### **Question 6 : Ajout de `changer_nombre_roues()`**  
Ajoutez une **méthode de classe `changer_nombre_roues(nouveau_nombre)`** pour modifier `nombre_roues`.

```plaintext
Définir une méthode de classe changer_nombre_roues(cls, nouveau_nombre)  
Modifier l'attribut de classe nombre_roues avec la nouvelle valeur  
Afficher une voiture avant et après le changement  
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
    nombre_roues = 4

    def __init__(self, marque, couleur):
        self.marque = marque
        self.couleur = couleur

    def decrire(self):
        return f"Cette voiture est une {self.marque} de couleur {self.couleur} avec {Voiture.nombre_roues} roues."

    @classmethod
    def changer_nombre_roues(cls, nouveau_nombre):
        cls.nombre_roues = nouveau_nombre

# Avant modification
v1 = Voiture("Toyota", "Bleu")
print("Avant :", v1.decrire())

# Modification
Voiture.changer_nombre_roues(6)

# Après modification
print("Après :", v1.decrire())
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - nombre_roues |  
+-----------------+
| + __init__()   |
| + decrire()    |
| + changer_nombre_roues() |  <-- Méthode de classe
+-----------------+
```
 
---

## **Partie 7 : Ajout d’un attribut privé**  

### **Question 7 : Ajout de `__kilometrage` et affichage**  

Ajoutez un **attribut privé `__kilometrage`** dans `__init__()`, puis créez une **méthode `afficher_kilometrage()`**.

```plaintext
Dans __init__(), ajouter un attribut privé __kilometrage  
Définir une méthode afficher_kilometrage()  
Retourner une phrase contenant la valeur de __kilometrage  
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
    nombre_roues = 4

    def __init__(self, marque, couleur, kilometrage):
        self.marque = marque
        self.couleur = couleur
        self.__kilometrage = kilometrage  # Attribut privé

    def afficher_kilometrage(self):
        return f"Le kilométrage de cette voiture est {self.__kilometrage} km."

v1 = Voiture("Toyota", "Bleu", 50000)
print(v1.afficher_kilometrage())  # Le kilométrage de cette voiture est 50000 km.
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - nombre_roues |  
| - __kilometrage |  <-- Attribut privé
+-----------------+
| + __init__()   |
| + afficher_kilometrage() |
+-----------------+
```

---

## **Partie 8 : Utilisation de `lambda` et des fonctions d'ordre supérieur**  

### **Question 8 : Ajout de `estimer_cout(lambda_function)`**  

Ajoutez une **méthode `estimer_cout(lambda_function)`** qui utilise une **fonction lambda** pour estimer le coût d'entretien.

```plaintext
Définir une méthode estimer_cout(self, lambda_function)  
Appliquer la fonction lambda sur __kilometrage et retourner le coût estimé  
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
    def __init__(self, marque, couleur, kilometrage):
        self.marque = marque
        self.couleur = couleur
        self.__kilometrage = kilometrage

    def estimer_cout(self, lambda_function):
        return lambda_function(self.__kilometrage)

v1 = Voiture("Toyota", "Bleu", 50000)
cout_estime = v1.estimer_cout(lambda km: km * 0.1)
print(f"Coût estimé d'entretien : {cout_estime} €")  # Coût estimé d'entretien : 5000 €
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - __kilometrage |  
+-----------------+
| + __init__()   |
| + estimer_cout(lambda_function) |  <-- Utilisation de lambda
+-----------------+
```

---

## **Partie 9 : Utilisation des compréhensions de liste avec `lambda`**  

### **Question 9 : Ajout de `estimer_couts_multiple()`**  

Ajoutez une **méthode `estimer_couts_multiple(prix_km, annees)`** qui retourne une **liste des coûts d'entretien** sur plusieurs années.

```plaintext
Définir une méthode estimer_couts_multiple(self, prix_km, annees)  
Retourner une liste des coûts d'entretien sur plusieurs années  
Utiliser une compréhension de liste et une fonction lambda  
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
    def __init__(self, marque, couleur, kilometrage):
        self.marque = marque
        self.couleur = couleur
        self.__kilometrage = kilometrage

    def estimer_couts_multiple(self, prix_km, annees):
        return [prix_km * self.__kilometrage * an for an in range(1, annees + 1)]

v1 = Voiture("Toyota", "Bleu", 50000)
couts = v1.estimer_couts_multiple(0.1, 5)
print(f"Coûts estimés sur 5 ans : {couts} €")
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - __kilometrage |  
+-----------------+
| + __init__()   |
| + estimer_couts_multiple(prix_km, annees) | <-- Compréhension de liste
+-----------------+
```

---

## **Partie 10 : Implémentation de `__str__`**  

### **Question 10 : Modifier `__str__` pour afficher une représentation détaillée**  
Ajoutez une méthode `__str__()` pour retourner une **chaîne formatée** des informations de la voiture.

```plaintext
Définir une méthode __str__(self)  
Retourner une chaîne formatée contenant marque, couleur, kilométrage et roues  
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
    def __init__(self, marque, couleur, kilometrage):
        self.marque = marque
        self.couleur = couleur
        self.__kilometrage = kilometrage

    def __str__(self):
        return f"Voiture {self.marque} de couleur {self.couleur} ayant parcouru {self.__kilometrage} km."

v1 = Voiture("Toyota", "Bleu", 50000)
print(v1)
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - __kilometrage |  
+-----------------+
| + __init__()   |
| + __str__() |  <-- Méthode spéciale
+-----------------+
```



---

## **Partie 11 : Implémentation de `__str__` avec affichage ASCII**  

### **Question 11 : Modifier `__str__` pour afficher une représentation ASCII détaillée**  
Modifiez `__str__()` pour **afficher un tableau ASCII bien formaté**.

```plaintext
Modifier __str__() pour afficher un tableau ASCII  
Inclure marque, couleur, kilométrage et roues  
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
    nombre_roues = 4

    def __init__(self, marque, couleur, kilometrage):
        self.marque = marque
        self.couleur = couleur
        self.__kilometrage = kilometrage

    def __str__(self):
        return f"""
-------------------------------
|         Informations        |
-------------------------------
| Marque      : {self.marque}   |
| Couleur     : {self.couleur}  |
| Kilométrage : {self.__kilometrage} km  |
| Roues       : {Voiture.nombre_roues}  |
-------------------------------
"""

v1 = Voiture("Tesla", "Rouge", 120000)
print(v1)
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - __kilometrage |  
| - nombre_roues  |
+-----------------+
| + __init__()   |
| + __str__()  |  <-- Affichage ASCII
+-----------------+
```

---

## **Partie 12 : Héritage simple**  

### **Question 12 : Création de `VoitureElectrique`**  
Ajoutez une **classe `VoitureElectrique` qui hérite de `Voiture`** et ajoute un attribut `autonomie`.  

```plaintext
Créer une classe VoitureElectrique qui hérite de Voiture  
Ajouter un attribut autonomie  
Ajouter une méthode afficher_autonomie()  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```python
class VoitureElectrique(Voiture):
    def __init__(self, marque, couleur, kilometrage, autonomie):
        super().__init__(marque, couleur, kilometrage)
        self.autonomie = autonomie

    def afficher_autonomie(self):
        return f"L'autonomie de cette voiture est de {self.autonomie} km."

v2 = VoitureElectrique("Nissan", "Blanc", 90000, 300)
print(v2.afficher_autonomie())
```

```
+-------------------------------+
|      VoitureElectrique        |
+-------------------------------+
| - marque                      |
| - couleur                     |
| - __kilometrage               |
| - autonomie                   |  <-- Nouvel attribut
+-------------------------------+
| + __init__()                  |
| + afficher_autonomie()         |
+-------------------------------+
```

---

## **Partie 13 : Utilisation de `super()` dans `VoitureElectrique`**  

### **Question 13 : Modifier `VoitureElectrique` pour utiliser `super()`**  
Modifiez la classe **`VoitureElectrique`** pour appeler **le constructeur de `Voiture` avec `super()`** et ajouter les informations d’autonomie dans **`__str__()`**.

```plaintext
Modifier __init__() pour appeler le constructeur parent avec super()  
Modifier __str__() pour appeler la méthode parent avec super().__str__()  
Ajouter les informations sur l'autonomie à la sortie  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```python
class VoitureElectrique(Voiture):
    def __init__(self, marque, couleur, kilometrage, autonomie):
        super().__init__(marque, couleur, kilometrage)
        self.autonomie = autonomie

    def __str__(self):
        return super().__str__() + f"| Autonomie   : {self.autonomie} km  |\n-------------------------------"

v3 = VoitureElectrique("Nissan", "Blanc", 90000, 300)
print(v3)
```

```
+-------------------------------+
|      VoitureElectrique        |
+-------------------------------+
| - marque                      |
| - couleur                     |
| - __kilometrage               |
| - autonomie                   |
+-------------------------------+
| + __init__()                  |  <-- Utilisation de super()
| + __str__()                   |  <-- Utilisation de super()
+-------------------------------+
```

---

## **Partie 14 : Héritage multiple avec `Batterie`**  

### **Question 14 : Ajout de `Batterie` et `VoitureElectriqueBatterie`**  

```plaintext
Créer une classe Batterie avec un attribut capacité  
Créer VoitureElectriqueBatterie qui hérite de VoitureElectrique et Batterie  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```python
class Batterie:
    def __init__(self, capacite):
        self.capacite = capacite

    def afficher_capacite(self):
        return f"La capacité de la batterie est de {self.capacite} kWh."

class VoitureElectriqueBatterie(VoitureElectrique, Batterie):
    def __init__(self, marque, couleur, kilometrage, autonomie, capacite):
        VoitureElectrique.__init__(self, marque, couleur, kilometrage, autonomie)
        Batterie.__init__(self, capacite)

    def __str__(self):
        return super().__str__() + f"\n| Batterie    : {self.capacite} kWh |\n-------------------------------"

v4 = VoitureElectriqueBatterie("Tesla", "Noir", 80000, 500, 75)
print(v4)
```

```
+-------------------------------+
|          Batterie             |
+-------------------------------+
| - capacité                    |
+-------------------------------+
| + __init__()                  |
| + afficher_capacite()          |
+-------------------------------+

+--------------------------------------+
|  VoitureElectriqueBatterie           |
+--------------------------------------+
| - autonomie                          |
| - capacité                           |
+--------------------------------------+
| + __init__()                         |
| + __str__()                           |
+--------------------------------------+
```

