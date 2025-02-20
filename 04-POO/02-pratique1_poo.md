---
title: "Pratique 1 - Introduction à la Programmation Orientée Objet en Python"
description: "Une introduction complète à la Programmation Orientée Objet en Python"
slug: "/python2/Introduction-to-OOP"
emoji: "📚"
---

# Pratique 1 - Introduction à la Programmation Orientée Objet en Python
*Une introduction à la Programmation Orientée Objet en Python.*  

---

<a name="table-des-matieres"></a>  
## **Table des matières**  

1. [Distinction entre classe et objet](#partie-1)  
2. [Définir une classe](#partie-2)  
3. [Créer un objet](#partie-3)  
4. [Accéder aux attributs et méthodes](#partie-4)  
5. [Attributs et méthodes d'instance](#partie-5)  
6. [Attributs et méthodes de classe](#partie-6)  
   6.1. [Attributs de classe](#partie-6-1)  
   6.2. [Méthodes de classe](#partie-6-2)  
7. [Constructeur `__init__`](#partie-7)  
8. [Héritage](#partie-8)  
9. [Polymorphisme](#partie-9]  

<br/>

---

<a name="partie-1"></a>  
## 01 - Distinction entre classe et objet  
---


<a name="partie-1-1"></a>  
#### Exercice 1 : Identifier la différence  
- Expliquez pourquoi `Avion` est une classe et pourquoi `avion1`, `avion2`, `avion3` sont des objets avec des attributs distincts.

[🔙 Retour à la table des matières](#table-des-matieres)  

<br/>

---
<a name="partie-2"></a>  
## 02 - Définir une classe  
---

<a name="partie-2-1"></a>  
#### Exercice 2.1 : Créer une classe Avion vide  
```python
class Avion:
    pass
```

[🔙 Retour à la table des matières](#table-des-matieres)  

<br/>

<a name="partie-2-2"></a>  
#### Exercice 2.2 : Ajouter des attributs au constructeur  
- Ajoutez `modele`, `capacite`, et `vitesse_max` au constructeur de la classe `Avion`.

```python
class Avion:
    def __init__(self, modele, capacite, vitesse_max):
        self.modele = modele
        self.capacite = capacite
        self.vitesse_max = vitesse_max
```

[🔙 Retour à la table des matières](#table-des-matieres)  

<br/>

---
<a name="partie-3"></a>  
## 03 - Créer un objet  
---

<a name="partie-3-1"></a>  
#### Exercice 3.1 : Créez trois avions avec 2 paramètres  
```python
avion1 = Avion("Airbus A320", 150, 800)
avion2 = Avion("Boeing 737", 180, 850)
avion3 = Avion("Concorde", 100, 2200)

print(avion1.modele, avion1.capacite, avion1.vitesse_max)
print(avion2.modele, avion2.capacite, avion2.vitesse_max)
print(avion3.modele, avion3.capacite, avion3.vitesse_max)
```

[🔙 Retour à la table des matières](#table-des-matieres)  

<br/>

<a name="partie-3-2"></a>  
#### Exercice 3.2 : Modifier le constructeur et tester la création d’instances  
- Ajoutez un attribut `portee_max` au constructeur et créez trois nouvelles instances avec ce paramètre.

```python
class Avion:
    def __init__(self, modele, capacite, vitesse_max, portee_max):
        self.modele = modele
        self.capacite = capacite
        self.vitesse_max = vitesse_max
        self.portee_max = portee_max

avion1 = Avion("Airbus A320", 150, 800, 6000)
avion2 = Avion("Boeing 737", 180, 850, 7000)
avion3 = Avion("Concorde", 100, 2200, 12000)

print(avion1.portee_max, avion2.portee_max, avion3.portee_max)
```

[🔙 Retour à la table des matières](#table-des-matieres)  

---

<a name="partie-4"></a>  
## 04 - Accéder aux attributs et méthodes  

#### Exercice 4.1 : Accédez et modifiez les attributs  
```python
avion1.vitesse_max = 830
print(avion1.vitesse_max)  # Vérifiez la nouvelle valeur
```

[🔙 Retour à la table des matières](#table-des-matieres)  

---

<a name="partie-5"></a>  
## 05 - Attributs et méthodes d'instance  

#### Exercice 5.1 : Ajoutez une méthode `decoller()`  
```python
class Avion:
    def __init__(self, modele, capacite, vitesse_max, portee_max):
        self.modele = modele
        self.capacite = capacite
        self.vitesse_max = vitesse_max
        self.portee_max = portee_max

    def decoller(self):
        print(f"L'avion {self.modele} décolle !")

avion1 = Avion("Airbus A380", 500, 900, 15000)
avion2 = Avion("Boeing 747", 400, 920, 14000)
avion3 = Avion("Concorde", 100, 2200, 12000)

avion1.decoller()
avion2.decoller()
avion3.decoller()
```

[🔙 Retour à la table des matières](#table-des-matieres)  

---

<a name="partie-6"></a>  
## 06 - Attributs et Méthodes de classe  

<a name="partie-6-1"></a>  
#### 6.1 Attributs de classe  
```python
class Avion:
    type_avion = "Aéronef"

print(Avion.type_avion)
```

[🔙 Retour à la table des matières](#table-des-matieres)  


<a name="partie-6-2"></a>  
#### 6.2 Méthodes de classe  
```python
class Avion:
    type_avion = "Aéronef"

    @classmethod
    def changer_type(cls, nouveau_type):
        cls.type_avion = nouveau_type

Avion.changer_type("Jet Privé")
print(Avion.type_avion)
```

[🔙 Retour à la table des matières](#table-des-matieres)  

---

<a name="partie-7"></a>  
## 07 - Constructeur `__init__`  
```python
class Avion:
    def __init__(self, modele, capacite, vitesse_max, portee_max, compagnie="Inconnue"):
        self.modele = modele
        self.capacite = capacite
        self.vitesse_max = vitesse_max
        self.portee_max = portee_max
        self.compagnie = compagnie

avion1 = Avion("Airbus A320", 150, 800, 6000)
avion2 = Avion("Boeing 747", 400, 920, 14000, "Air France")
avion3 = Avion("Concorde", 100, 2200, 12000, "British Airways")

print(avion1.compagnie, avion2.compagnie, avion3.compagnie)
```

[🔙 Retour à la table des matières](#table-des-matieres)  





<a name="partie-"></a>  
## 08 - Multiples Constructeurs dans une Classe  

*Dans cette section, nous allons créer plusieurs constructeurs dans la même classe pour gérer différentes façons d'initialiser un objet.*  

#### Exercice 8.1 : Ajouter plusieurs constructeurs  

- Créez une classe `Avion` avec :  

1. Un constructeur sans paramètres.  
2. Un constructeur avec 2 paramètres.  
3. Un constructeur avec 4 paramètres.  

```python
class Avion:
    def __init__(self, modele=None, capacite=None, vitesse_max=None, portee_max=None):
        if modele is None and capacite is None:
            print("Avion par défaut créé.")
        elif vitesse_max is None and portee_max is None:
            self.modele = modele
            self.capacite = capacite
            print(f"Avion {self.modele} avec capacité de {self.capacite} passagers créé.")
        else:
            self.modele = modele
            self.capacite = capacite
            self.vitesse_max = vitesse_max
            self.portee_max = portee_max
            print(f"Avion {self.modele}, capacité : {self.capacite}, vitesse max : {self.vitesse_max} km/h, portée : {self.portee_max} km créé.")

# Créez des instances avec différents constructeurs
avion1 = Avion()  # Sans paramètres
avion2 = Avion("Airbus A320", 150)  # Avec 2 paramètres
avion3 = Avion("Concorde", 100, 2200, 12000)  # Avec 4 paramètres
```

#### Explication  
- Le constructeur utilise des valeurs par défaut `None` pour permettre plusieurs types d'initialisation.  
- En fonction des paramètres passés, la classe choisit quel bloc exécuter.  
- Cela simule plusieurs constructeurs dans une même classe Python.



[🔙 Retour à la table des matières](#table-des-matieres)  

