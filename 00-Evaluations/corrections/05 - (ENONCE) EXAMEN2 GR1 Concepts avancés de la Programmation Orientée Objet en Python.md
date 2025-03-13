# **Examen Avancé : Programmation Orientée Objet en Python**  

## **Règles**
- Réécrivez le code complet pour chaque question.
- Chaque question s’appuie sur la précédente et modifie la classe pour la rendre plus complète.
- Les erreurs de conception doivent être détectées et corrigées en intégrant des assertions et des exceptions.
- Vous ne devez pas modifier le code des classes parent sans justification.

---

## **Partie 1 : Création et amélioration d'une classe**

### **Question 1 : Classe `Vehicule` minimale avec `pass`**
Définissez une classe `Vehicule` avec une structure minimale pour éviter les erreurs de syntaxe.

```python
...........................................................
...........................................................
```

---

### **Question 2 : Ajout de `__init__` et des attributs privés**
Ajoutez les attributs privés `__marque` et `__modele` dans le constructeur `__init__()` de `Vehicule`.  
Puis, instanciez un objet et affichez ses attributs.

```python
...........................................................
...........................................................
...........................................................
```

---

### **Question 3 : Getters et Setters avec vérification**
Ajoutez des getters et setters pour `__marque` et `__modele`, en empêchant l'affectation d'une valeur vide.

```python
...........................................................
...........................................................
```

Test attendu :
```python
v = Vehicule("Toyota", "Corolla")
v.set_marque("")
```
Doit lever une exception : `ValueError: La marque ne peut pas être vide.`

---

## **Partie 2 : Héritage et polymorphisme**

### **Question 4 : Classe `Voiture` héritant de `Vehicule`**
Créez une classe `Voiture` qui hérite de `Vehicule` et ajoute l’attribut `__kilometrage`.  
Ajoutez un getter et un setter avec vérification (le kilométrage ne peut être négatif).

```python
...........................................................
...........................................................
```

Test attendu :
```python
v = Voiture("BMW", "X5", 120000)
v.set_kilometrage(-500)
```
Doit lever une exception : `ValueError: Le kilométrage ne peut pas être négatif.`

---

### **Question 5 : Surcharge de `__str__`**
Ajoutez `__str__()` dans `Vehicule` et `Voiture` pour afficher les informations complètes.

```python
...........................................................
...........................................................
```

Output attendu :
```
Véhicule: Toyota Corolla
Voiture: BMW X5, 120000 km
```

---

### **Question 6 : Classe `Camion` avec surcharge de `__init__`**
Créez une classe `Camion` qui hérite de `Vehicule` et ajoute un attribut `__charge_max` (charge maximale en tonnes).  
Utilisez `super()` dans `__init__()`.

```python
...........................................................
...........................................................
```

Test attendu :
```python
c = Camion("Renault", "Magnum", 25)
print(c)
```
Output attendu :
```
Camion: Renault Magnum, Charge Max : 25 tonnes
```

---

## **Partie 3 : Méthodes de classe et statiques**

### **Question 7 : Attribut de classe `nb_vehicules` et méthode de classe**
Ajoutez un attribut de classe `nb_vehicules` qui compte les instances de `Vehicule`.  
Ajoutez une méthode de classe `nombre_de_vehicules()` pour retourner ce nombre.

```python
...........................................................
...........................................................
```

Test attendu :
```python
v1 = Voiture("Toyota", "Yaris", 80000)
v2 = Camion("Mercedes", "Actros", 30)
print(Vehicule.nombre_de_vehicules())
```
Output attendu : `2`

---

## **Partie 4 : Encapsulation avancée et méthodes magiques**

### **Question 8 : Protéger l’accès aux attributs avec `property`**
Utilisez `@property` et `@setter` pour `__kilometrage` dans `Voiture`.

```python
...........................................................
...........................................................
```

Test attendu :
```python
v = Voiture("Ford", "Focus", 60000)
print(v.kilometrage)
v.kilometrage = -1000
```
Doit lever une exception : `ValueError: Le kilométrage ne peut pas être négatif.`

---

### **Question 9 : Comparaison d’objets (`__eq__`, `__lt__`, `__gt__`)**
Ajoutez `__eq__`, `__lt__` et `__gt__` dans `Voiture` pour comparer les kilométrages.

```python
...........................................................
...........................................................
```

Test attendu :
```python
v1 = Voiture("Peugeot", "208", 50000)
v2 = Voiture("Renault", "Clio", 60000)
print(v1 < v2)
```
Output attendu : `True`

---

## **Partie 5 : Héritage multiple et décorateurs**

### **Question 10 : Classe `Electrique` avec héritage multiple**
Créez une classe `Electrique` avec un attribut `__autonomie` et faites en sorte que `VoitureElectrique` hérite à la fois de `Voiture` et `Electrique`.

```python
...........................................................
...........................................................
```

Test attendu :
```python
ve = VoitureElectrique("Tesla", "Model 3", 30000, 450)
print(ve)
```
Output attendu :
```
Voiture Électrique: Tesla Model 3, 30000 km, 450 km autonomie
```

---

### **Question 11 : Méthode statique `est_eco_friendly()`**
Ajoutez une méthode statique `est_eco_friendly()` qui retourne `True` pour `VoitureElectrique` et `False` pour `Camion`.

```python
...........................................................
...........................................................
```

Test attendu :
```python
print(VoitureElectrique.est_eco_friendly())  # True
print(Camion.est_eco_friendly())            # False
```

---

## **Partie 6 : Métaclasses et Annotations**

### **Question 12 : Métaclasse `VehiculeMeta` pour forcer l’implémentation de `__str__`**
Créez une métaclasse `VehiculeMeta` qui interdit de créer une classe sans méthode `__str__()`.

```python
...........................................................
...........................................................
```

Test attendu :
```python
class Moto(Vehicule):
    pass
```
Doit lever une erreur : `TypeError: La classe Moto doit implémenter __str__().`

---

### **Question 13 : Annotation des types dans `Voiture`**
Ajoutez des annotations de type dans `Voiture` (`marque: str`, `modele: str`, `kilometrage: int`).

```python
...........................................................
...........................................................
```

Test attendu :
```python
v = Voiture("Audi", "A3", "trente mille")
```
Doit lever une erreur : `TypeError: kilometrage doit être un entier.`

---

## **Fin de l'examen**  
Notions évaluées :  
- Encapsulation avancée  
- Héritage multiple  
- Surcharge de méthodes spéciales  
- Gestion des erreurs avec des exceptions  
- Métaclasses et annotations  

Cet examen demande réflexion, rigueur et compréhension avancée de la POO en Python.

