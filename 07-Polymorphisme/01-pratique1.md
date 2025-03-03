### **Pratique Complète : Héritage et Surcharge de Méthode en Python**

### **Exemple détaillé : Héritage et surcharge de méthode**

#### **Scénario : Gestion des animaux**
Nous allons créer une classe `Animal` qui représente un animal générique. Ensuite, nous définirons les classes `Chien` et `Chat` qui hériteront de `Animal`. Nous illustrerons :
1. **L’héritage** → Les sous-classes `Chien` et `Chat` récupèrent les caractéristiques de `Animal`.
2. **La surcharge de méthode** → Chaque sous-classe redéfinit la méthode `parler()` avec un comportement spécifique.

---

#### **Code de base :**
```python
# Définition de la classe Animal
class Animal:
    def __init__(self, nom):
        self.nom = nom

    def parler(self):
        return "Je suis un animal, je fais un son."

# Définition de la classe Chien qui hérite de Animal
class Chien(Animal):
    def parler(self):  # Redéfinition de la méthode parler
        return "Ouaf ! Ouaf !"

# Définition de la classe Chat qui hérite de Animal
class Chat(Animal):
    def parler(self):  # Redéfinition de la méthode parler
        return "Miaou ! Miaou !"

# Création des objets
animal = Animal("Générique")
chien = Chien("Rex")
chat = Chat("Minou")

# Affichage des résultats
print(animal.nom, ":", animal.parler())  # Affiche : Générique : Je suis un animal, je fais un son.
print(chien.nom, ":", chien.parler())    # Affiche : Rex : Ouaf ! Ouaf !
print(chat.nom, ":", chat.parler())      # Affiche : Minou : Miaou ! Miaou !
```

---

### **Explications :**
1. La classe `Animal` est une classe mère avec un attribut `nom` et une méthode `parler()`.
2. `Chien` et `Chat` héritent de `Animal` et redéfinissent la méthode `parler()`.
3. Chaque instance utilise la méthode appropriée selon sa classe.

---

## **Exercices progressifs**
Les exercices suivent une progression logique et claire. Les emplacements à modifier sont indiqués.

---

### **Exercice 1 : Compléter la classe `Oiseau`**
**Objectif :** Ajouter une classe `Oiseau` qui hérite de `Animal` et surcharge `parler()` pour retourner `"Cui Cui !"`.

**Instructions :**
1. Complétez la définition de la classe `Oiseau`.
2. Ajoutez une surcharge de la méthode `parler()`.

**Code à compléter :**
```python
class Animal:
    def __init__(self, nom):
        self.nom = nom

    def parler(self):
        return "Je suis un animal, je fais un son."

class Chien(Animal):
    def parler(self):
        return "Ouaf ! Ouaf !"

class Chat(Animal):
    def parler(self):
        return "Miaou ! Miaou !"

# À compléter : Créer la classe Oiseau en héritant de Animal
class Oiseau(Animal):
    def parler(self):
        # Modifier ici pour retourner "Cui Cui !"
        pass  

# Test de la classe Oiseau
oiseau = Oiseau("Tweety")
print(oiseau.nom, ":", oiseau.parler())  # Doit afficher : Tweety : Cui Cui !
```

---

### **Exercice 2 : Ajouter un attribut `age`**
**Objectif :** Modifier la classe `Animal` pour inclure un attribut `age`.

**Instructions :**
1. Ajoutez un paramètre `age` dans le constructeur `__init__()`.
2. Créez une instance de `Chien` avec un âge et affichez son nom et son âge.

**Code à compléter :**
```python
class Animal:
    def __init__(self, nom):  # Modifier ici pour ajouter un paramètre age
        self.nom = nom
        # Ajouter une ligne ici pour stocker l'âge

    def parler(self):
        return "Je suis un animal, je fais un son."

class Chien(Animal):
    def parler(self):
        return "Ouaf ! Ouaf !"

class Chat(Animal):
    def parler(self):
        return "Miaou ! Miaou !"

# À compléter : Créer un chien avec un nom et un âge
chien = Chien("Max", 5)  # Modifier ici pour ajouter l'âge
print(f"{chien.nom} a {chien.age} ans.")  # Doit afficher : Max a 5 ans.
```

---

### **Exercice 3 : Appeler la méthode parent avec `super()`**
**Objectif :** Utiliser `super()` pour appeler la méthode `parler()` de `Animal` avant d’ajouter `"Cui Cui !"` dans `Oiseau`.

**Instructions :**
1. Utilisez `super().parler()` pour récupérer le comportement de la classe `Animal`.
2. Ajoutez `" Cui Cui !"` après cet appel.

**Code à compléter :**
```python
class Oiseau(Animal):
    def parler(self):
        # Modifier ici pour appeler super().parler() et ajouter " Cui Cui !"
        pass  

oiseau = Oiseau("Tweety", 2)
print(oiseau.nom, ":", oiseau.parler())  # Doit afficher : Tweety : Je suis un animal, je fais un son. Cui Cui !
```

---

### **Exercice 4 : Ajouter une méthode spéciale `__str__()`**
**Objectif :** Ajouter une méthode `__str__()` pour afficher un animal sous forme de texte.

**Instructions :**
1. Ajoutez `__str__()` à `Animal` pour afficher `"Animal: Nom, Age ans"`.
2. Ajoutez `__str__()` à `Chien` pour afficher `"Chien: Nom, Age ans"`.

**Code à compléter :**
```python
class Animal:
    def __init__(self, nom, age):
        self.nom = nom
        self.age = age

    def __str__(self):
        # Modifier ici pour retourner "Animal: Nom, Age ans"
        pass  

class Chien(Animal):
    def parler(self):
        return "Ouaf ! Ouaf !"

    def __str__(self):
        # Modifier ici pour retourner "Chien: Nom, Age ans"
        pass  

chien = Chien("Rex", 4)
print(chien)  # Doit afficher : Chien: Rex, 4 ans
```

---

### **Exercice 5 : Ajouter une nouvelle classe `Serpent`**
**Objectif :** Créer une classe `Serpent` qui hérite de `Animal` avec :
1. Une surcharge de `parler()` qui affiche `"Ssss Ssss !"`.
2. Une méthode `ramper()` qui affiche `"Le serpent rampe silencieusement..."`.

**Instructions :**
1. Ajoutez une classe `Serpent` qui hérite de `Animal`.
2. Surchargez `parler()`.
3. Ajoutez une méthode `ramper()`.

**Code à compléter :**
```python
# À compléter : Définir la classe Serpent qui hérite de Animal
class Serpent(Animal):
    def parler(self):
        # Modifier ici pour retourner "Ssss Ssss !"
        pass  

    def ramper(self):
        # Modifier ici pour retourner "Le serpent rampe silencieusement..."
        pass  

serpent = Serpent("Kaa", 3)
print(serpent.nom, ":", serpent.parler())  # Doit afficher : Kaa : Ssss Ssss !
print(serpent.ramper())  # Doit afficher : Le serpent rampe silencieusement...
```

---

### **Conclusion**
- L’héritage permet de réutiliser le code d’une classe mère dans une sous-classe.
- La surcharge de méthode permet de modifier un comportement hérité.
- Ces exercices progressifs vous aideront à bien comprendre ces concepts.
