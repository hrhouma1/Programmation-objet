# **Examen : Programmation Orientée Objet en Python**  

## **Règles :**  
- **Réécrivez le code complet** pour chaque question.  
- **Chaque question s’appuie sur la précédente** et enrichit la classe progressivement.  
- **Aucune exception** ne doit être levée. Utilisez **if, else et while** pour la validation.  
- **Encapsulation, getters/setters, surcharge, héritage simple et multiple, et polymorphisme** sont **obligatoires**.  

---

## **Partie 1 : Création et encapsulation d'une classe**

### **Question 1 : Définition de la classe `Vehicule` avec encapsulation**
**Énoncé :**  
- Définissez une classe `Vehicule` avec trois **attributs privés** :  
  - `marque` (chaîne de caractères)  
  - `modele` (chaîne de caractères)  
  - `kilometrage` (nombre entier)  
- Ajoutez un **constructeur `__init__()`** pour initialiser ces valeurs.

```python
...........................................................
...........................................................
```

---

### **Question 2 : Getters et Setters avec validation simple**  
**Énoncé :**  
- Ajoutez **des getters et setters** pour `kilometrage`.  
- **Validation** : Si `kilometrage` est négatif, mettez-le à `0` à l’aide d’un `if`.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", -100)
print(v.get_kilometrage())  # Doit afficher 0 car un kilométrage négatif n'est pas autorisé
```

---

### **Question 3 : Affichage des informations du véhicule**  
**Énoncé :**  
- Ajoutez une **méthode `afficher_infos()`** qui affiche les informations du véhicule sous la forme :  
  `"Marque: Toyota | Modèle: Corolla | Kilométrage: 100000 km"`  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", 100000)
v.afficher_infos()
# Doit afficher : "Marque: Toyota | Modèle: Corolla | Kilométrage: 100000 km"
```

---

## **Partie 2 : Héritage et polymorphisme**

### **Question 4 : Classe `Voiture` qui hérite de `Vehicule` avec surcharge**  
**Énoncé :**  
- Créez une classe `Voiture` qui hérite de `Vehicule`.  
- Ajoutez un **attribut privé** `nombre_portes` (par défaut `4`).  
- **Ajoutez un setter** pour `nombre_portes` avec validation :  
  - Si `nombre_portes` est inférieur à `2`, mettez `2`.  
  - Si `nombre_portes` est supérieur à `5`, mettez `5`.  
- **Surchargez** la méthode `afficher_infos()` pour inclure `nombre_portes`.

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Voiture("Toyota", "Corolla", 100000, 6)
v.afficher_infos()
# Doit afficher : "Marque: Toyota | Modèle: Corolla | Kilométrage: 100000 km | Portes: 5"
```

---

### **Question 5 : Classe `Camion` qui hérite de `Vehicule` avec surcharge**  
**Énoncé :**  
- Créez une classe `Camion` qui hérite de `Vehicule`.  
- Ajoutez un **attribut privé** `charge_max` (en tonnes, par défaut `5`).  
- **Ajoutez un setter** pour `charge_max` avec validation :  
  - Si `charge_max` est inférieur à `1`, mettez `1`.  
  - Si `charge_max` est supérieur à `20`, mettez `20`.  
- **Surchargez** `afficher_infos()` pour inclure `charge_max`.

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
c = Camion("Volvo", "FH16", 200000, 25)
c.afficher_infos()
# Doit afficher : "Marque: Volvo | Modèle: FH16 | Kilométrage: 200000 km | Charge max: 20 tonnes"
```

---

## **Partie 3 : Héritage multiple et gestion des erreurs avec if/else**

### **Question 6 : Classe `Electrique` avec héritage multiple**  
**Énoncé :**  
- Créez une classe `Electrique` avec un **attribut privé** `autonomie` (en km, par défaut `300`).  
- Ajoutez un **getter et setter** avec validation :  
  - Si `autonomie` est inférieur à `50`, mettez `50`.  
  - Si `autonomie` est supérieur à `800`, mettez `800`.  
- Créez une **classe `VoitureElectrique`** qui hérite à la fois de `Voiture` et `Electrique`.  
- Surchargez `afficher_infos()` pour inclure `autonomie`.

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
ve = VoitureElectrique("Tesla", "Model 3", 50000, 4, 900)
ve.afficher_infos()
# Doit afficher : "Marque: Tesla | Modèle: Model 3 | Kilométrage: 50000 km | Portes: 4 | Autonomie: 800 km"
```

---

## **Partie 4 : Encapsulation avancée et boucles while**

### **Question 7 : Méthode `ajouter_kilometrage()` avec boucle `while`**  
**Énoncé :**  
- Ajoutez une méthode `ajouter_kilometrage()` qui permet **d’ajouter du kilométrage**.  
- Si la valeur est négative, utilisez **une boucle `while`** pour demander une valeur valide.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", 50000)
v.ajouter_kilometrage(-1000)  
# Doit redemander une valeur tant que celle-ci est négative
```

---

### **Question 8 : Méthode `verifier_entretien()` avec conditions if/else**  
**Énoncé :**  
- Ajoutez une méthode `verifier_entretien()` qui retourne :  
  - `"Entretien recommandé"` si `kilometrage > 100000`  
  - `"Entretien non nécessaire"` sinon.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", 120000)
print(v.verifier_entretien())  # Doit afficher : "Entretien recommandé"
```

---

### **Question 9 : Comparaison d’objets (`__lt__`, `__gt__`)**  
**Énoncé :**  
- Ajoutez `__lt__` et `__gt__` dans `Vehicule` pour comparer les kilométrages.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v1 = Vehicule("Peugeot", "208", 50000)
v2 = Vehicule("Renault", "Clio", 60000)
print(v1 < v2)  # True
```












## **Partie 5 : Méthodes spéciales et visibilité des attributs**

### **Question 10 : Surcharge de `__str__` pour un affichage amélioré**  
**Énoncé :**  
- Ajoutez **`__str__`** dans `Vehicule` pour afficher proprement les informations du véhicule.  
- Remplacez `afficher_infos()` par un simple `print(objet)`.  

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", 75000)
print(v)
# Doit afficher : "Toyota Corolla - 75000 km"
```

---

### **Question 11 : Protection avancée des attributs privés avec `__nom_attribut`**  
**Énoncé :**  
- Modifiez `Vehicule` pour que `marque`, `modele` et `kilometrage` soient **réellement privés** (`__marque`, `__modele`, `__kilometrage`).  
- Ajoutez des **getters et setters** adaptés pour accéder aux données sans casser le programme.

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", 50000)
print(v.__marque)  # Doit lever une erreur (l'attribut est privé)
print(v.get_marque())  # Doit afficher "Toyota"
```

---

### **Question 12 : Méthode `__eq__` pour comparer deux véhicules**  
**Énoncé :**  
- Implémentez **`__eq__`** pour comparer deux objets `Vehicule` en fonction de leur **marque, modèle et kilométrage**.

#### **Test attendu :**  
```python
v1 = Vehicule("Toyota", "Corolla", 50000)
v2 = Vehicule("Toyota", "Corolla", 50000)
print(v1 == v2)  # Doit afficher True
```

---

### **Question 13 : Interdiction de modifier directement les attributs privés**  
**Énoncé :**  
- Empêchez la modification directe de `kilometrage` en levant une exception si quelqu’un essaie `v.kilometrage = 1000`.  
- Assurez-vous que la seule façon de modifier le kilométrage est via le setter.

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", 50000)
v.kilometrage = 1000  # Doit lever une exception
```

---

### **Question 14 : Classe `Garage` qui stocke plusieurs véhicules**  
**Énoncé :**  
- Créez une classe `Garage` qui contient une **liste de véhicules**.  
- Ajoutez une méthode `ajouter_vehicule(v)` pour stocker les objets `Vehicule`.  
- Ajoutez une méthode `__len__` pour renvoyer le nombre de véhicules.

#### **Test attendu :**  
```python
g = Garage()
g.ajouter_vehicule(Vehicule("Toyota", "Yaris", 30000))
g.ajouter_vehicule(Vehicule("Ford", "Focus", 50000))
print(len(g))  # Doit afficher 2
```

---

### **Question 15 : Classe `Location` avec gestion des véhicules loués**  
**Énoncé :**  
- Créez une classe `Location` avec une liste de **véhicules en location**.  
- Ajoutez une méthode `louer_vehicule(v)` qui ne permet de louer que si le kilométrage est **inférieur à 200000 km**.  
- Ajoutez une méthode `retourner_vehicule(v)` pour le remettre en stock.

#### **Test attendu :**  
```python
l = Location()
v1 = Vehicule("Peugeot", "308", 180000)
v2 = Vehicule("Renault", "Clio", 210000)

l.louer_vehicule(v1)  # OK
l.louer_vehicule(v2)  # Doit afficher un message d'erreur
```

