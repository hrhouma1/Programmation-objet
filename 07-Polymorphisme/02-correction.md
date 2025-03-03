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


# Annexe -exercice 4  (méthode de Yoan)

### **Explication de `__str__()` et `self.__class__.__name__`**

#### **1. Rôle de `__str__()`**
La méthode `__str__()` est une **méthode spéciale** qui définit comment un objet doit être représenté sous forme de **chaîne de caractères** lorsqu'il est passé à `print()` ou `str()`.  
Sans cette méthode, `print(objet)` afficherait une représentation générique comme `<__main__.Animal object at 0x...>`.

---

#### **2. Utilisation de `self.__class__.__name__`**
```python
def __str__(self):
    return f"{self.__class__.__name__}: {self.nom}, {self.age} ans"
```
- `self.__class__` retourne la **classe** de l’objet (`Animal`, `Chien`, etc.).
- `self.__class__.__name__` récupère **le nom** de cette classe sous forme de chaîne (`"Animal"`, `"Chien"`, etc.).
- Cela permet d’afficher automatiquement le nom correct de la classe sans avoir à le coder en dur.

---

### **3. Pourquoi utiliser `self.__class__.__name__` ?**
- **Évite la répétition** : On n’a pas besoin d’écrire une méthode `__str__()` différente dans chaque sous-classe.
- **S’adapte dynamiquement** : Si `Chien` hérite de `Animal`, alors `print(chien)` affichera `"Chien: Rex, 4 ans"` sans avoir besoin de redéfinir `__str__()` dans `Chien`.

---

### **4. Illustration avec un exemple**
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

# Création d'objets
animal = Animal("Animal", 1)
chien = Chien("Rex", 4)

# Affichage
print(animal)  # Affiche : Animal: Animal, 1 ans
print(chien)   # Affiche : Chien: Rex, 4 ans
```

---

### **Conclusion**
L’utilisation de `self.__class__.__name__` permet d’adapter automatiquement la méthode `__str__()` aux classes dérivées, ce qui simplifie le code et évite les répétitions inutiles.



