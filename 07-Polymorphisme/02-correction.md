### **Correction des exercices**



### **Correction de l’Exercice 1 : Compléter la classe `Oiseau`**
```python
class Oiseau(Animal):
    def parler(self):
        return "Cui Cui !"
```
✅ **Correction appliquée** : La méthode `parler()` retourne `"Cui Cui !"` comme attendu.

---

### **Correction de l’Exercice 2 : Ajouter un attribut `age`**
```python
class Animal:
    def __init__(self, nom, age):  # Ajout du paramètre `age`
        self.nom = nom
        self.age = age  # Stockage de l'âge

    def parler(self):
        return "Je suis un animal, je fais un son."

class Chien(Animal):
    def parler(self):
        return "Ouaf ! Ouaf !"

class Chat(Animal):
    def parler(self):
        return "Miaou ! Miaou !"

# Création d'un chien avec un nom et un âge
chien = Chien("Max", 5)  
print(f"{chien.nom} a {chien.age} ans.")  # Affiche : Max a 5 ans.
```
✅ **Correction appliquée** : `age` est maintenant pris en compte dans le constructeur et affiché correctement.

---

### **Correction de l’Exercice 3 : Appeler la méthode parent avec `super()`**
```python
class Oiseau(Animal):
    def parler(self):
        return super().parler() + " Cui Cui !"
```
✅ **Correction appliquée** : `super().parler()` récupère la version de la classe mère et ajoute `" Cui Cui !"`.

---

### **Correction de l’Exercice 4 : Ajouter une méthode spéciale `__str__()`**
```python
class Animal:
    def __init__(self, nom, age):
        self.nom = nom
        self.age = age

    def __str__(self):
        return f"Animal: {self.nom}, {self.age} ans"

class Chien(Animal):
    def parler(self):
        return "Ouaf ! Ouaf !"

    def __str__(self):
        return f"Chien: {self.nom}, {self.age} ans"

animal = Animal("Animal", 1)
print (animal)
chien = Chien("Rex", 4)
print(chien)  # Affiche : Chien: Rex, 4 ans
```
✅ **Correction appliquée** : La méthode `__str__()` retourne maintenant un affichage formaté correctement.


## Variante 2 - Méthode de Yoan

```python
class Animal:
    def __init__(self, nom, age):
        self.nom = nom
        self.age = age

    def __str__(self):
        return f"{self.__class__.__name__}: {self.nom}, {self.age} ans"

class Chien(Animal):
    def parler(self):
        return "Ouaf ! Ouaf !"

animal = Animal("Animal", 1)
chien = Chien("Rex", 4)
print (animal)
print(chien)  # Affiche : Chien: Rex, 4 ans
```

---

### **Correction de l’Exercice 5 : Ajouter une nouvelle classe `Serpent`**
```python
class Serpent(Animal):
    def parler(self):
        return "Ssss Ssss !"

    def ramper(self):
        return "Le serpent rampe silencieusement..."

serpent = Serpent("Kaa", 3)
print(serpent.nom, ":", serpent.parler())  # Affiche : Kaa : Ssss Ssss !
print(serpent.ramper())  # Affiche : Le serpent rampe silencieusement...
```
✅ **Correction appliquée** : `Serpent` hérite bien de `Animal`, surcharge `parler()` et ajoute `ramper()`.

