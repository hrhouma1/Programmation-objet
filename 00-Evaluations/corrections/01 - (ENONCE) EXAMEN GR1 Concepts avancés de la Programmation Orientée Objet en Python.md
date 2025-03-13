# **Examen 1 : Concepts avancés de la Programmation Orientée Objet en Python**  

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

📌 **💡 Output attendu :**  
```
Cette voiture est une Toyota de couleur Bleu avec 4 roues.
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

📌 **💡 Output attendu :**  
```
Avant modification : Cette voiture est une Toyota de couleur Bleu avec 4 roues.
Après modification : Cette voiture est une Toyota de couleur Bleu avec 6 roues.
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

📌 **💡 Output attendu :**  
```
Le kilométrage de cette voiture est 50000 km.
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
| + decrire()    |
| + changer_nombre_roues() |
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

📌 **💡 Output attendu :**  
```
Coût estimé d'entretien : 5000 €
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - nombre_roues |  
| - __kilometrage |  
+-----------------+
| + __init__()   |
| + decrire()    |
| + changer_nombre_roues() |
| + afficher_kilometrage() |
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

📌 **💡 Output attendu :**  
```
Coûts estimés sur 5 ans : [5000, 10000, 15000, 20000, 25000] €
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - nombre_roues |  
| - __kilometrage |  
+-----------------+
| + __init__()   |
| + decrire()    |
| + changer_nombre_roues() |
| + afficher_kilometrage() |
| + estimer_cout(lambda_function) |
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

📌 **💡 Output attendu :**  
```
Voiture Toyota de couleur Bleu ayant parcouru 50000 km.
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - nombre_roues |  
| - __kilometrage |  
+-----------------+
| + __init__()   |
| + decrire()    |
| + changer_nombre_roues() |
| + afficher_kilometrage() |
| + estimer_cout(lambda_function) |
| + estimer_couts_multiple(prix_km, annees) |
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

📌 **💡 Output attendu :**  
```
-------------------------------
|         Informations        |
-------------------------------
| Marque      : Tesla         |
| Couleur     : Rouge         |
| Kilométrage : 120000 km     |
| Roues       : 4             |
-------------------------------
```

```
+-----------------+
|    Voiture     |
+-----------------+
| - marque       |
| - couleur      |
| - nombre_roues |  
| - __kilometrage |  
+-----------------+
| + __init__()   |
| + decrire()    |
| + changer_nombre_roues() |
| + afficher_kilometrage() |
| + estimer_cout(lambda_function) |
| + estimer_couts_multiple(prix_km, annees) |
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

```
+-------------------------------+
|      VoitureElectrique        |
+-------------------------------+
| - marque                      |
| - couleur                     |
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

📌 **💡 Output attendu :**  
```
-------------------------------
|         Informations        |
-------------------------------
| Marque      : Nissan        |
| Couleur     : Blanc         |
| Kilométrage : 90000 km      |
| Roues       : 4             |
| Type        : Électrique    |
| Autonomie   : 300 km        |
-------------------------------
```

```
+-------------------------------+
|      VoitureElectrique        |
+-------------------------------+
| - marque                      |
| - couleur                     |
| - __kilometrage                |
| - autonomie                    |
+-------------------------------+
| + __init__()                  |  <-- Utilisation de super()
| + decrire()                   |
| + __str__()                   |  <-- Utilisation de super()
| + afficher_autonomie()         |
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

---

## **Partie 15 : Vérification des types avec `type()`, `isinstance()` et `issubclass()`**  

```plaintext
Définir une méthode de classe verifier_type(cls, objet)  
Utiliser type() pour afficher le type exact de l’objet  
Utiliser isinstance(objet, Voiture) pour vérifier si l’objet est une instance  
Utiliser issubclass(VoitureElectrique, Voiture) pour vérifier l’héritage  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
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
| + verifier_type(objet)  |
+-----------------+
```

---


### **Partie 16 : Récapitulatif – Getters, Setters et Héritage**  

### **Question 16 : Création et modification de plusieurs types de voitures**  

Créez plusieurs types de voitures (`Voiture`, `VoitureElectrique`, `VoitureElectriqueBatterie`) avec des valeurs différentes.  
Utilisez des **getters et setters** pour accéder et modifier l’attribut privé `__kilometrage`.  
Enfin, affichez les informations de toutes les voitures créées.  

```plaintext
Définir des getters et setters pour l'attribut __kilometrage  
Créer 5 voitures de différents types  
Modifier le kilométrage de certaines voitures avec le setter  
Afficher les informations de chaque voiture  
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
-------------------------------
|         Informations        |
-------------------------------
| Marque      : Toyota        |
| Couleur     : Bleu          |
| Kilométrage : 50000 km      |
| Roues       : 4             |
-------------------------------

-------------------------------
|         Informations        |
-------------------------------
| Marque      : Tesla         |
| Couleur     : Rouge         |
| Kilométrage : 125000 km     |
| Roues       : 4             |
| Type        : Électrique    |
| Autonomie   : 400 km        |
-------------------------------

-------------------------------
|         Informations        |
-------------------------------
| Marque      : BMW           |
| Couleur     : Noir          |
| Kilométrage : 80000 km      |
| Roues       : 4             |
-------------------------------

-------------------------------
|         Informations        |
-------------------------------
| Marque      : Audi          |
| Couleur     : Gris          |
| Kilométrage : 65000 km      |
| Roues       : 4             |
| Type        : Électrique    |
| Autonomie   : 60000 km      |
| Batterie    : 75 kWh        |
-------------------------------

-------------------------------
|         Informations        |
-------------------------------
| Marque      : Nissan        |
| Couleur     : Blanc         |
| Kilométrage : 90000 km      |
| Roues       : 4             |
| Type        : Électrique    |
| Autonomie   : 300 km        |
-------------------------------
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
| + decrire()    |
| + get_kilometrage() |
| + set_kilometrage() |
+-----------------+

+-------------------------------+
|      VoitureElectrique        |
+-------------------------------+
| - marque                      |
| - couleur                     |
| - autonomie                   |
| - __kilometrage                |
+-------------------------------+
| + __init__()                  |
| + afficher_autonomie()         |
| + get_kilometrage()            |
| + set_kilometrage()            |
+-------------------------------+

+--------------------------------------+
|  VoitureElectriqueBatterie           |
+--------------------------------------+
| - autonomie                          |
| - capacité                           |
| - __kilometrage                      |
+--------------------------------------+
| + __init__()                         |
| + afficher_autonomie()               |
| + afficher_capacite()                 |
| + get_kilometrage()                   |
| + set_kilometrage()                   |
+--------------------------------------+
```

**Ce que cette question teste :**  
- **Encapsulation** (`__kilometrage`, `get_kilometrage()`, `set_kilometrage()`).  
- **Héritage** (`VoitureElectrique`, `VoitureElectriqueBatterie`).  
- **Utilisation de `super()`** pour appeler `__str__()` de la classe parente.  
- **Modification contrôlée des attributs avec des setters**.  
- **Affichage clair et structuré des informations des véhicules**.  
