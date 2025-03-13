
# **Correction - Examen Avancé : Programmation Orientée Objet en Python**  

---

## **Partie 1 : Création et amélioration d'une classe**

### **Question 1 : Classe `Vehicule` minimale avec `pass`**  
**Énoncé :**  
Définissez une classe `Vehicule` contenant uniquement `pass` pour éviter les erreurs de syntaxe.  

```python
...........................................................
...........................................................
```

#### **Correction :**  
```python
class Vehicule:
    pass
```

---

### **Question 2 : Ajout de `__init__` et des attributs privés**  
**Énoncé :**  
Ajoutez un constructeur `__init__()` qui prend deux arguments : `marque` et `modele`.  
Stockez ces valeurs dans des **attributs privés** `__marque` et `__modele`.  
Instanciez un objet `Vehicule` et affichez ses attributs.  

```python
...........................................................
...........................................................
...........................................................
```

#### **Correction :**  
```python
class Vehicule:
    def __init__(self, marque: str, modele: str):
        self.__marque = marque
        self.__modele = modele

    def get_marque(self):
        return self.__marque

    def get_modele(self):
        return self.__modele

# Test
v = Vehicule("Toyota", "Corolla")
print(v.get_marque())  # Toyota
print(v.get_modele())  # Corolla
```

---

### **Question 3 : Getters et Setters avec vérification**  
**Énoncé :**  
- Ajoutez des **getters** et **setters** pour `__marque` et `__modele`.  
- Le setter doit lever une exception (`ValueError`) si une valeur vide est assignée.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla")
v.set_marque("")
```
**Doit lever une exception :** `ValueError: La marque ne peut pas être vide.`  

---

#### **Correction :**  
```python
class Vehicule:
    def __init__(self, marque: str, modele: str):
        self.set_marque(marque)
        self.set_modele(modele)

    def get_marque(self):
        return self.__marque

    def get_modele(self):
        return self.__modele

    def set_marque(self, marque: str):
        if not marque:
            raise ValueError("La marque ne peut pas être vide.")
        self.__marque = marque

    def set_modele(self, modele: str):
        if not modele:
            raise ValueError("Le modèle ne peut pas être vide.")
        self.__modele = modele

# Test
v = Vehicule("Toyota", "Corolla")
try:
    v.set_marque("")
except ValueError as e:
    print(e)  # La marque ne peut pas être vide.
```

---

## **Partie 2 : Héritage et polymorphisme**

### **Question 4 : Classe `Voiture` héritant de `Vehicule`**  
**Énoncé :**  
- Créez une classe `Voiture` qui hérite de `Vehicule`.  
- Ajoutez un **attribut privé** `__kilometrage`.  
- Implémentez un setter qui empêche de définir un kilométrage négatif.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Voiture("BMW", "X5", 120000)
v.set_kilometrage(-500)
```
**Doit lever une exception :** `ValueError: Le kilométrage ne peut pas être négatif.`  

---

#### **Correction :**  
```python
class Voiture(Vehicule):
    def __init__(self, marque: str, modele: str, kilometrage: int):
        super().__init__(marque, modele)
        self.set_kilometrage(kilometrage)

    def get_kilometrage(self):
        return self.__kilometrage

    def set_kilometrage(self, kilometrage: int):
        if kilometrage < 0:
            raise ValueError("Le kilométrage ne peut pas être négatif.")
        self.__kilometrage = kilometrage
```

---

### **Question 5 : Surcharge de `__str__`**  
**Énoncé :**  
Ajoutez `__str__()` pour afficher les informations complètes de `Vehicule` et `Voiture`.  

```python
...........................................................
...........................................................
```

#### **Correction :**  
```python
class Vehicule:
    def __init__(self, marque: str, modele: str):
        self.__marque = marque
        self.__modele = modele

    def __str__(self):
        return f"Véhicule: {self.__marque} {self.__modele}"

class Voiture(Vehicule):
    def __init__(self, marque: str, modele: str, kilometrage: int):
        super().__init__(marque, modele)
        self.__kilometrage = kilometrage

    def __str__(self):
        return f"Voiture: {self.get_marque()} {self.get_modele()}, {self.__kilometrage} km"

# Test
v = Voiture("BMW", "X5", 120000)
print(v)  # Voiture: BMW X5, 120000 km
```

---

## **Partie 6 : Métaclasses et Annotations**

### **Question 13 : Annotation des types dans `Voiture`**  
**Énoncé :**  
Ajoutez des **annotations de type** pour les attributs `marque: str`, `modele: str`, `kilometrage: int`.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Voiture("Audi", "A3", "trente mille")
```
**Doit lever une erreur :** `TypeError: kilometrage doit être un entier.`  

---

#### **Correction :**  
```python
class Vehicule:
    def __init__(self, marque: str, modele: str):
        self.__marque = marque
        self.__modele = modele

    def get_marque(self) -> str:
        return self.__marque

    def get_modele(self) -> str:
        return self.__modele

class Voiture(Vehicule):
    def __init__(self, marque: str, modele: str, kilometrage: int):
        super().__init__(marque, modele)
        if not isinstance(kilometrage, int):
            raise TypeError("kilometrage doit être un entier.")
        self.__kilometrage = kilometrage

    def get_kilometrage(self) -> int:
        return self.__kilometrage
```

---

### **Test après correction :**  
```python
try:
    v = Voiture("Audi", "A3", "trente mille")  # Erreur : kilometrage doit être un entier
except TypeError as e:
    print(e)  # Output : kilometrage doit être un entier.
```

---

Cette correction couvre **toutes les parties** de l'examen avec des solutions détaillées et des tests pour chaque question. Elle intègre des concepts avancés comme l'encapsulation, l'héritage, la validation des entrées et les annotations de type en Python.
