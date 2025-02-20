---  
title: "Théorie 1 - Introduction à la Programmation Orientée Objet en Python"  
description: "Une introduction complète à la Programmation Orientée Objet en Python"
slug: "/docs/python2/week4/theory1"
emoji: "📚"  
---  

# Introduction à la Programmation Orientée Objet en Python
*Un guide complet pour débutants sur la Programmation Orientée Objet en Python.*

---

<a name="table-des-matieres"></a>
## Table des matières

1. [Distinction entre classe et objet](#partie-1)
2. [Définir une classe](#partie-2) 
3. [Créer un objet](#partie-3)
4. [Accéder aux attributs et méthodes](#partie-4)
5. [Attributs et méthodes d'instance](#partie-5)
6. [Attributs et méthodes de classe](#partie-6)
7. [Constructeur `__init__`](#partie-7)
8. [Exercice - Multiples Constructeurs dans une Classe](#partie-8)
9. [La méthode __str__](#partie-9)
10. [Héritage](#partie-10)
11. [Polymorphisme](#partie-11)
12. [Conclusion](#partie-12)



<a name="partie-1"></a>
<br/>
---
## 01 - Distinction entre classe et objet
---
Une classe est un modèle ou un plan qui définit la structure et le comportement des objets. On peut la voir comme un plan de construction pour un objet, un blueprint, un template, un type de données personnalisé, etc ...
Elle spécifie les attributs (données) et les méthodes (fonctions) que les objets de cette classe posséderont. Un objet est une instance concrète d'une classe, avec ses propres valeurs d'attributs.

Par exemple, si nous avons une classe Voiture, elle définit la structure générale d'une voiture (marque, modèle, couleur, etc.). Chaque voiture spécifique créée à partir de cette classe est un objet distinct avec ses propres caractéristiques.
Disons que l'instance est la concrétisation de la classe, la réalité.

:::info Exemple
Si un professeur est dans une classe et qu'il appelle simplement "Élève", personne ne répondra. Par contre, s'il appelle "Alexandre", l'élève concerné répondra. Cela illustre que "Élève" est un blueprint (une classe) tandis qu'"Alexandre" est une instance concrète de la classe Élève. De la même façon qu'une classe définit un modèle général, et une instance représente un cas spécifique et réel de ce modèle.
:::


[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-2"></a>
<br/>
---
## 02 - Définir une classe
---

En Python, une classe se définit avec le mot-clé `class`. Voici un exemple simple :

```python
class Voiture:
    def __init__(self, marque, modele, couleur):
        self.marque = marque
        self.modele = modele
        self.couleur = couleur
```

- Si vous voulez en savoir plus sur la classe `__init__`, vous pouvez consulter le point suivant (point 07).
- Si vous voulez en savoir plus sur la classe `self`, vous pouvez consulter le point suivant (point 05).

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-3"></a>
<br/>
---
## 03 - Créer un objet
---

Pour créer un objet de la classe Voiture, nous appelons simplement la classe comme une fonction (pas besoin du mot-clé `new` comme dans d'autres langages) :

```python
ma_voiture = Voiture("Toyota", "Corolla", "Rouge")
```

Pour créer un deuxième objet de la classe Voiture, nous appelons simplement la classe comme une fonction :

```python
ma_voiture2 = Voiture("Renault", "Clio", "Bleue")
```




[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-4"></a>
<br/>
---
## 04 - Accéder aux attributs et méthodes
---

Pour accéder aux attributs et méthodes d'un objet, nous utilisons le point (`.`) :

```python
ma_voiture = Voiture("Toyota", "Corolla", "Rouge")
print(ma_voiture.marque)  # Affiche "Toyota"
ma_voiture.accelerer()    # Appelle la méthode accelerer()
```



:::info Accès aux attributs et méthodes d'instance
- Vous remarquez que nous avons utilisé le point (`.`) pour accéder aux attributs de l'objet.
- Vous remarquez aussi que les propriétés sont différentes pour chaque instance : `ma_voiture1`, `ma_voiture2` et `ma_voiture3`.
- On appelle cela des attributs d'instance car ils sont propres à chaque instance (objet) créée à partir de la classe.
- Chaque objet possède ses propres valeurs d'attributs qui sont indépendantes des autres objets.
- Pour appeler la méthode `accelerer` pour chaque objet, nous pouvons utiliser le code suivant :
:::

:::danger Création des objets :
:::

```python
ma_voiture1 = Voiture("Toyota", "Corolla", "Rouge")
ma_voiture2 = Voiture("Renault", "Clio", "Bleue")
ma_voiture3 = Voiture("Peugeot", "208", "Verte")
```

:::danger accès aux attributs :
:::

```python
ma_voiture1 = ma_voiture1.nom
ma_voiture2 = ma_voiture2.nom
ma_voiture3 = ma_voiture3.nom
print(ma_voiture1)
print(ma_voiture2)
print(ma_voiture3)
```

:::danger appel des méthodes :
:::

```python
ma_voiture1.accelerer()    # Appelle la méthode accelerer()
ma_voiture2.accelerer()    # Appelle la méthode accelerer()
ma_voiture3.accelerer()    # Appelle la méthode accelerer()
```



[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-5"></a>
<br/>

---
## 05 - Attributs et méthodes d'instance
---

Il y a deux types d'attributs et de méthodes :
- Les attributs et méthodes d'instance
- Les attributs et méthodes de classe


Les attributs d'instance sont propres à chaque instance (objet) créée à partir de la classe.
Les méthodes d'instance sont des fonctions définies dans une classe qui peuvent accéder et modifier les attributs de l'objet. Elles prennent toujours `self` comme premier paramètre. Le mot `self` est une convention pour faire référence à l'objet courant lui-même. si ma ma_voiture1 est une instance de la classe Voiture, alors `self` sera la ma_voiture1 elle-même.

Exemple : 

```python
class Voiture:
    def __init__(self, marque, modele, couleur):
        self.marque = marque
        self.modele = modele
        self.couleur = couleur

    def accelerer(self):
        print(f"{self.marque} {self.modele} accélère.")

ma_voiture1 = Voiture("Toyota", "Corolla", "Rouge")
ma_voiture2 = Voiture("Renault", "Clio", "Bleue")

# Ma voiture 1 est une première instance de la classe Voiture
# Ma voiture 2 est une deuxième instance de la classe Voiture
# Les attributs d'instance sont propres à chaque instance (objet) créée à partir de la classe.
# Les méthodes d'instance sont des fonctions définies dans une classe qui peuvent accéder et modifier les attributs de l'objet. Elles prennent toujours `self` comme premier paramètre.
# Les attributs d'instance de ma_voiture1 sont différents de ceux de ma_voiture2.
# Les méthodes d'instance de ma_voiture1 sont différentes de celles de ma_voiture2. Chaque méthode d'instance est liée à l'objet spécifique qui l'appelle et utilise ses propres attributs.

# Attributs d'instance
print(ma_voiture1.marque) # Affiche : Toyota
print(ma_voiture2.marque) # Affiche : Renault et non pas Toyota.

# Méthodes d'instance
ma_voiture1.accelerer() # Affiche : Toyota Corolla accélère.
ma_voiture2.accelerer() # Affiche : Renault Clio accélère et non pas Toyota Corolla.
```

:::info Mot clé self
Ici le mot clé self va faire référence à l'objet courant ma_voiture1 et ensuite à ma_voiture2.
:::



Les attributs de classe sont partagés par toutes les instances de la classe.
Les méthodes de classe sont des fonctions définies dans une classe qui peuvent accéder et modifier les attributs de la classe. Elles prennent toujours `cls` comme premier paramètre. Nous verrons plus de détails sur les attributs et méthodes de classe au point suivant (point 06).

Pour bien comprendre la différence entre les attributs/méthodes d'instance et de classe, prenons une analogie simple :
Imaginez une usine qui fabrique des voitures (la classe). Chaque voiture produite (instance) aura :

**Attributs et méthodes d'instance :**
- Propres à chaque voiture individuelle
- Exemple : la couleur, le numéro de série
- Chaque voiture peut avoir une couleur différente

**Attributs et méthodes de classe : (nous verrons cela plus tard au point 06)**
- Partagés par TOUTES les voitures
- Exemple : le nom du constructeur, le nombre total de voitures produites
- Si on change le nom du constructeur, ça change pour toutes les voitures

Maintenant, mettons en pratique ces concepts avec un exemple concret de code :

```python
class Voiture:
    def __init__(self, marque, modele, couleur):
        self.marque = marque
        self.modele = modele
        self.couleur = couleur

    def accelerer(self):
        print(f"{self.marque} {self.modele} accélère.")
```



Nous créons trois voitures différentes (3 instances), chacune avec ses propres attributs :

```python
ma_voiture1 = Voiture("Toyota", "Corolla", "Rouge") # Création de la première voiture (instance 1)
ma_voiture2 = Voiture("Renault", "Clio", "Bleue") # Création de la deuxième voiture (instance 2)
ma_voiture3 = Voiture("Peugeot", "208", "Verte") # Création de la troisième voiture (instance 3)
```
Pour afficher les marques , nous pouvons utiliser le code suivant :

```python
print(ma_voiture1.marque)  # Affiche "Toyota"
print(ma_voiture2.marque)  # Affiche "Renault"
print(ma_voiture3.marque)  # Affiche "Peugeot"
```



:::info Résumé des attributs d'instance et méthodes d'instance
- Les attributs d'instance sont des variables définies directement dans la classe. Elles sont propres à chaque instance (objet) créée à partir de la classe.
- Les méthodes d'instance sont des fonctions définies dans une classe qui peuvent accéder et modifier les attributs de l'objet. Elles prennent toujours `self` comme premier paramètre.
:::





[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-6"></a>
<br/>

---
## 06 - Attributs et Méthodes de classe
---

### *6.1. Attributs de classe*
Les attributs de classe sont des variables définies directement dans la classe, plutôt que dans une instance spécifique. Ils sont partagés par toutes les instances de la classe.

:::info Attribut de classe
Un attribut de classe est une variable définie directement dans la classe, plutôt que dans une instance spécifique. Ils sont partagés par toutes les instances de la classe.
:::

```python
class Voiture:
    vitesse_max = 200  # Attribut de classe

    def __init__(self, marque, modele, couleur):
        self.marque = marque
        self.modele = modele
        self.couleur = couleur

```

Pour accéder à l'attribut de classe, nous pouvons utiliser le code suivant :

```python
print(Voiture.vitesse_max)  # Affiche 200
```

Vous remarquez que nous n'avons pas besoin d'instancier une classe pour accéder à l'attribut de classe (Voiture avec un V en majuscule qui est le nom de la classe).


[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-6-2"></a>
<br/>

### *6.2. Méthodes de classe*
Les méthodes de classe sont des fonctions définies dans une classe qui peuvent accéder et modifier les attributs de la classe. Elles prennent toujours `cls` comme premier paramètre.


```python
class Voiture:
    vitesse_max = 200  # Attribut de classe

    def __init__(self, marque, modele, couleur):
        self.marque = marque
        self.modele = modele
        self.couleur = couleur

    @classmethod
    def changer_vitesse_max(cls, nouvelle_vitesse):
        cls.vitesse_max = nouvelle_vitesse  

```

Pour appeler la méthode de classe, nous pouvons utiliser le code suivant :

```python
Voiture.changer_vitesse_max(250)
```


Vous remarquez que nous n'avons pas besoin d'instancier une classe pour appeler la méthode de classe (Voiture avec un V en majuscule qui est le nom de la classe).

:::info Méthode de classe
Une méthode de classe est une fonction définie dans une classe qui peut accéder et modifier les attributs de la classe. Elles prennent toujours `cls` comme premier paramètre.
:::


Je vais vous donner deux exemples d'instances voiture 1 et voiture 2 et montre peu importe l'instance, la vitesse max sera la même.

```python
voiture1 = Voiture("Toyota", "Corolla", "Rouge")
voiture2 = Voiture("Renault", "Clio", "Bleue")


# Voiture 1
print(voiture1.vitesse_max) # Affiche 250

# Voiture 2
print(voiture2.vitesse_max) # Affiche 250
```

```python
Voiture.changer_vitesse_max(300)

# Voiture 1
print(voiture1.vitesse_max) # Affiche 300

# Voiture 2
print(voiture2.vitesse_max) # Affiche 300
```

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-7"></a>
<br/>

---
## 07 - Constructeur `__init__`
---

Le constructeur `__init__` est une méthode spéciale qui est appelée lors de la création d'un objet. Il est utilisé pour initialiser les attributs de l'objet.

```python
class Voiture:
    def __init__(self, la_marque, le_modele, la_couleur):
        self.marque = la_marque
        self.modele = le_modele
        self.couleur = la_couleur
```

Créons deux  instance de la classe Voiture :

```python
voiture1 = Voiture("Toyota", "Corolla", "Rouge")
voiture2 = Voiture("Renault", "Clio", "Bleue")
```

Vous remarquez que nous avons passé 3 paramètres `marque`, `modele` et `couleur` à la méthode `__init__` lors de la création de chaque instance. En effet, la méthode `__init__` est une méthode spéciale qui est appelée lors de la création d'un objet. Dans sa définition, nous avons défini trois paramètres `marque`, `modele` et `couleur`. Prenons un autre exemple avec 5 paramètres :

```python
class Voiture:
    def __init__(self, la_marque, le_modele, la_couleur, la_vitesse_max, la_acceleration):
        self.marque = la_marque
        self.modele = le_modele
        self.couleur = la_couleur
        self.vitesse_max = la_vitesse_max
        self.acceleration = la_acceleration
```

Créons deux  instance de la classe Voiture :

```python
voiture1 = Voiture("Toyota", "Corolla", "Rouge", 200, 10)
voiture2 = Voiture("Renault", "Clio", "Bleue", 220, 12)
```

Vous remarquez que nous avons passé 5 paramètres `marque`, `modele`, `couleur`, `vitesse_max` et `acceleration` à la méthode `__init__` lors de la création de chaque instance. En effet, dans la nouvelle définition de la classe, nous avons défini cinq paramètres `marque`, `modele`, `couleur`, `vitesse_max` et `acceleration` dans la méthode `__init__`. Du coup, nous devons passer 5 paramètres lors de la création de chaque instance.


❌ Ce qu'il ne pas faire ❌ :

```python
voiture1 = Voiture("Toyota", "Corolla")
```

```python
voiture1 = Voiture("Toyota", "Corolla", "Rouge")
```

ou encore :

```python
voiture1 = Voiture("Toyota", "Corolla", "Rouge", 200)
```

Pourquoi ❓

Parce que dans la définition de la classe, nous avons défini 5 paramètres `marque`, `modele`, `couleur` et `vitesse_max`, `acceleration`. Du coup, nous devons passer 5 paramètres lors de la création de chaque instance.

:::danger Attention
- Si vous ne passez pas les bons paramètres, vous aurez une erreur.
- Quand vous créez une instance de la classe, vous devez passer les bons paramètres et le bon nombre de paramètres.
- Si vous ne passez pas le bon nombre de paramètres, vous aurez une erreur.
- Quand vous écrivez voiture1 = Voiture("Toyota", "Corolla", "Rouge", 200, 10), vous dites à Python que vous voulez créer une instance de la classe Voiture avec les paramètres "Toyota", "Corolla", "Rouge" , vitesse de 200 et une accélération de 10. Python va donc appeler la méthode `__init__` avec ces 5 paramètres.
- Quand vous écrivez voiture1 = Voiture("Toyota", "Corolla", "Rouge"), vous dites à Python que vous voulez créer une instance de la classe Voiture avec les paramètres "Toyota", "Corolla", "Rouge". Python va donc appeler la méthode `__init__` avec ces 3 paramètres. Ceci n'est pas correct car la méthode `__init__` attend 5 paramètres.
:::




[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-8"></a>
<br/>

---
## 08 - Exercice - Multiples Constructeurs dans une Classe
---


###  08.1 - Objectif 

Implémenter une classe `Voiture` avec plusieurs façons de créer des objets en Python. Dans cette section, nous allons créer plusieurs constructeurs dans la même classe pour gérer différentes façons d'initialiser un objet.

En Python, bien qu'il n'y ait techniquement qu'un seul constructeur (`__init__`), nous pouvons simuler plusieurs constructeurs en utilisant des méthodes de classe (`@classmethod`). Cette approche nous permet d'avoir différentes façons d'initialiser nos objets selon les besoins.

Par exemple, nous pourrions vouloir créer une voiture :
- Avec tous les détails (constructeur standard)
- Uniquement avec la marque (constructeur simplifié)
- Avec des valeurs par défaut (constructeur par défaut)

Cette flexibilité nous permet d'adapter la création d'objets selon le contexte d'utilisation.

[� Retour à la table des matières](#table-des-matieres)
<a name="partie-8-2"></a>
<br/>

### 08.2 - Instructions 

#### 08.2.1. **Crée une classe `Voiture`** avec les attributs :
   - `marque`
   - `modele`
   - `annee`

#### 08.2.2. **Ajoute un constructeur standard** (`__init__`) qui initialise ces trois attributs.

#### 08.2.3. **Ajoute un constructeur alternatif** en utilisant `@classmethod` :
   - `depuis_marque(cls, marque)` : crée un objet avec une marque donnée, et utilise des valeurs par défaut pour le modèle (`"Modèle inconnu"`) et l’année (`2022`).

#### 08.2.4. **Ajoute un autre constructeur alternatif** :
   - `voiture_par_defaut(cls)` : crée un objet avec des valeurs par défaut (`Toyota`, `Corolla`, `2022`).

#### 08.2.5. **Ajoute une méthode** `afficher_details(self)` pour afficher les informations de la voiture.



#### *Ce que tu dois faire :*
- **Écrire le code complet de la classe**.
- **Créer au moins trois instances** :
1. Une en utilisant le constructeur standard.
2. Une en utilisant le constructeur `depuis_marque`.
3. Une en utilisant le constructeur `voiture_par_defaut`.
- **Afficher les détails de chaque instance.**



#### *Défi supplémentaire :*
- Modifie l’un des constructeurs pour permettre d’ajouter un nouvel attribut `couleur` avec une valeur par défaut, et crée une nouvelle instance avec cette modification.



#### *Exemple de sortie attendue :*
```
Voiture: BMW X5, Année: 2021
Voiture: Audi Modèle inconnu, Année: 2022
Voiture: Toyota Corolla, Année: 2022
```



[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-8-3"></a>
<br/>




### 8.3 - Solution : Classe `Voiture` avec multiples constructeurs

```python
class Voiture:
    def __init__(self, marque, modele, annee):
        self.marque = marque
        self.modele = modele
        self.annee = annee

    @classmethod
    def depuis_marque(cls, marque):
        """Constructeur alternatif : initialise avec la marque, et des valeurs par défaut pour modèle et année."""
        return cls(marque, "Modèle inconnu", 2022)

    @classmethod
    def voiture_par_defaut(cls):
        """Constructeur alternatif : initialise avec des valeurs par défaut."""
        return cls("Toyota", "Corolla", 2022)

    def afficher_details(self):
        """Affiche les informations de la voiture."""
        print(f"Voiture: {self.marque} {self.modele}, Année: {self.annee}")


# Création d'instances avec différentes méthodes de construction
voiture1 = Voiture("BMW", "X5", 2021)                    # Constructeur standard
voiture2 = Voiture.depuis_marque("Audi")                 # Constructeur alternatif avec marque
voiture3 = Voiture.voiture_par_defaut()                  # Constructeur alternatif avec valeurs par défaut

# Affichage des détails
voiture1.afficher_details()
voiture2.afficher_details()
voiture3.afficher_details()
```


[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-8-4"></a>
<br/>


### 8.4 - Défi supplémentaire : Ajouter un attribut `couleur`

```python
class Voiture:
    def __init__(self, marque, modele, annee, couleur="Blanc"):
        self.marque = marque
        self.modele = modele
        self.annee = annee
        self.couleur = couleur

    @classmethod
    def depuis_marque(cls, marque, couleur="Blanc"):
        return cls(marque, "Modèle inconnu", 2022, couleur)

    @classmethod
    def voiture_par_defaut(cls):
        return cls("Toyota", "Corolla", 2022, "Rouge")

    def afficher_details(self):
        print(f"Voiture: {self.marque} {self.modele}, Année: {self.annee}, Couleur: {self.couleur}")


# Création d'instances avec l'attribut couleur
voiture1 = Voiture("Mercedes", "Classe A", 2020, "Noir")
voiture2 = Voiture.depuis_marque("Ford", "Bleu")
voiture3 = Voiture.voiture_par_defaut()

voiture1.afficher_details()
voiture2.afficher_details()
voiture3.afficher_details()
```


[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-8-5"></a>
<br/>


### 8.5 - Exemple de sortie attendue :
```
Voiture: BMW X5, Année: 2021
Voiture: Audi Modèle inconnu, Année: 2022
Voiture: Toyota Corolla, Année: 2022
```



[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-9"></a>
<br/>

---
## 09 - La méthode `__str__` 🖋️
---

La méthode `__str__` est une méthode spéciale en Python qui permet de définir la représentation sous forme de chaîne de caractères d'un objet. Elle rend l'affichage des objets plus lisible et convivial, souvent utilisée pour le débogage ou l'affichage à l'utilisateur.


### 09.1 - Exemple sans `__str__` :

```python
class Voiture:
    def __init__(self, marque, modele, couleur):
        self.marque = marque
        self.modele = modele
        self.couleur = couleur

# Création d'un objet
ma_voiture = Voiture("Toyota", "Corolla", "Rouge")

# Affichage de l'objet
print(ma_voiture)
```

#### 09.1.1 - Sortie :
```
<__main__.Voiture object at 0x7f8b3c1d2e10>
```
> *Sans la méthode `__str__`, Python affiche l'adresse mémoire de l'objet, ce qui n'est pas très lisible pour l'utilisateur.*


[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-9-2"></a>
<br/>


### 09.2 - Exemple avec `__str__` :

```python
class Voiture:
    def __init__(self, marque, modele, couleur):
        self.marque = marque
        self.modele = modele
        self.couleur = couleur

    def __str__(self):
        return f"{self.marque} {self.modele} ({self.couleur})"

# Création d'un objet
ma_voiture = Voiture("Toyota", "Corolla", "Rouge")

# Affichage de l'objet
print(ma_voiture)
```

#### 09.2.1 - Sortie :
```
Toyota Corolla (Rouge)
```
> *Avec la méthode `__str__`, l'objet est affiché de manière plus lisible et explicite !*

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-9-3"></a>
<br/>



### 09.3 - Exercice : Ajoute `__str__` à une classe existante

#### 09.3.1 - Instructions :
1. Crée une classe `Personne` avec les attributs `nom`, `prenom` et `age`.
2. Ajoute un constructeur `__init__` pour initialiser ces attributs.
3. Affiche un objet de cette classe sans méthode `__str__`.
4. Ajoute ensuite la méthode `__str__` pour afficher une phrase comme :
   ```
   Jean Dupont, 30 ans
   ```


[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-9-4"></a>
<br/>


### 09.4 - Défi supplémentaire :
- Modifie la méthode `__str__` pour qu'elle affiche une phrase complète, par exemple :
  ```
  Bonjour, je m'appelle Jean Dupont et j'ai 30 ans.
  ```


[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10"></a>
<br/>

---
## 10 - Héritage 🧬
---

L’héritage est l’un des concepts fondamentaux de la **Programmation Orientée Objet (POO)**. Il permet à une classe de **réutiliser** et **étendre** les fonctionnalités d'une autre classe. Avec l'héritage, nous pouvons éviter la duplication de code et rendre nos programmes plus organisés et faciles à maintenir.


Dans cette section, nous allons :
- Comprendre le concept d’héritage et pourquoi il est utile.
- Savoir comment créer une classe parente et une classe fille.
- Découvrir comment utiliser `super()` pour hériter des attributs et méthodes.
- Apprendre à surcharger des méthodes dans une classe fille.
- Mettre en pratique l’héritage avec des exercices guidés.






[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10-1"></a>
<br/>


---
### 10.1 - Qu'est-ce que l'héritage ? 
---

L'héritage est un mécanisme qui permet à une classe (**classe fille**) de reprendre les attributs et méthodes d'une autre classe (**classe parente**). La classe fille peut :
- Utiliser directement les attributs et méthodes de la classe parente.
- Ajouter ses propres attributs et méthodes.
- Modifier les méthodes de la classe parente.

**Exemple du monde réel :**
- Une classe `Animal` peut avoir des attributs comme `nom` et `age`, et une méthode `manger()`.
- Une classe `Chien` peut hériter de `Animal` et ajouter un attribut `race` et une méthode `aboyer()`.






[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10-2"></a>
<br/>

---
### 10.2 - Créer une classe parente 
---

Avant de créer une classe fille, nous avons besoin d'une classe parente. Voici une classe `Voiture` :

```python
class Voiture:
    def __init__(self, marque, modele, couleur):
        self.marque = marque
        self.modele = modele
        self.couleur = couleur

    def afficher_details(self):
        print(f"{self.marque} {self.modele} ({self.couleur})")
```

Cette classe `Voiture` possède :
- Un **constructeur `__init__`** qui initialise `marque`, `modele` et `couleur`.
- Une **méthode `afficher_details`** pour afficher les informations d'une voiture.



[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10-3"></a>
<br/>


---
### 10.3 - Créer une classe fille 
---

Nous pouvons créer une classe fille `VoitureSportive` qui hérite de `Voiture` :

```python
class VoitureSportive(Voiture):
    def __init__(self, marque, modele, couleur, vitesse_max):
        super().__init__(marque, modele, couleur)  # Appelle le constructeur de la classe parente
        self.vitesse_max = vitesse_max

    def afficher_details(self):
        super().afficher_details()  # Utilise la méthode de la classe parente
        print(f"Vitesse max : {self.vitesse_max} km/h")
```

**Que se passe-t-il ici ?**
- `class VoitureSportive(Voiture)` : signifie que `VoitureSportive` **hérite** de `Voiture`.
- `super().__init__(...)` : permet d’appeler le constructeur de la classe parente.
- `self.vitesse_max` : nouvel attribut propre à `VoitureSportive`.
- `super().afficher_details()` : réutilise la méthode de la classe parente.




[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10-4"></a>
<br/>

---
### 10.4 - Utilisation de `super()` 
---

La fonction `super()` est essentielle dans l'héritage. Elle permet :
- **D’appeler les méthodes de la classe parente**.
- D’éviter de réécrire du code déjà existant.
- D’assurer que la classe parente est correctement initialisée.

**Sans `super()` :**
```python
class VoitureSportive(Voiture):
    def __init__(self, marque, modele, couleur, vitesse_max):
        self.marque = marque  # Répétition de code
        self.modele = modele
        self.couleur = couleur
        self.vitesse_max = vitesse_max
```

**Avec `super()` :**
```python
class VoitureSportive(Voiture):
    def __init__(self, marque, modele, couleur, vitesse_max):
        super().__init__(marque, modele, couleur)  # Réutilisation du code parent
        self.vitesse_max = vitesse_max
```



[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10-5"></a>
<br/>

---
### 10.5 - Surcharge de méthodes 
---

La **surcharge de méthodes** signifie qu’une méthode définie dans la classe fille peut **remplacer** celle de la classe parente.

**Exemple :**
```python
class Voiture:
    def accelerer(self):
        print("La voiture accélère.")

class VoitureSportive(Voiture):
    def accelerer(self):
        print("La voiture sportive accélère rapidement !")
```

**Comment ça fonctionne ?**
- Si vous appelez `accelerer()` sur une `VoitureSportive`, c'est la méthode de la classe fille qui est utilisée.
- Mais vous pouvez toujours appeler la méthode parente avec `super().accelerer()`.



[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10-6"></a>
<br/>



---
### 10.6 - Avantages de l'héritage
---

- **Réutilisation de code** : Pas besoin de réécrire du code commun.
- **Extensibilité** : Ajoute facilement de nouvelles fonctionnalités.
- **Organisation** : Code plus propre et plus structuré.
- **Polymorphisme** : Les classes filles peuvent être utilisées comme des classes parentes, rendant le code flexible.


[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10-7"></a>
<br/>

---
### 10.7 - Exercice pratique 
---

#### **Instructions :**
1. Crée une classe `Animal` avec :
   - Un constructeur `__init__` prenant `nom` et `age`.
   - Une méthode `faire_du_bruit()` qui affiche `"L'animal fait du bruit."`.
2. Crée une classe `Chien` qui hérite de `Animal` :
   - Ajoute un attribut `race`.
   - Surcharge la méthode `faire_du_bruit()` pour afficher `"Le chien aboie."`.
3. Crée une classe `Chat` qui hérite de `Animal` :
   - Ajoute un attribut `couleur`.
   - Surcharge la méthode `faire_du_bruit()` pour afficher `"Le chat miaule."`.

#### **Ce que tu dois faire :**
- Crée des objets `Chien` et `Chat` avec différents attributs.
- Affiche les détails de chaque animal.
- Appelle la méthode `faire_du_bruit()` pour chaque objet.




[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-10-8"></a>
<br/>


---
### 10.8 - Solution de l'exercice 
---

```python
class Animal:
    def __init__(self, nom, age):
        self.nom = nom
        self.age = age

    def faire_du_bruit(self):
        print("L'animal fait du bruit.")

class Chien(Animal):
    def __init__(self, nom, age, race):
        super().__init__(nom, age)
        self.race = race

    def faire_du_bruit(self):
        print("Le chien aboie.")

class Chat(Animal):
    def __init__(self, nom, age, couleur):
        super().__init__(nom, age)
        self.couleur = couleur

    def faire_du_bruit(self):
        print("Le chat miaule.")

# Création d'objets
mon_chien = Chien("Rex", 5, "Berger Allemand")
mon_chat = Chat("Minou", 3, "Noir")

# Affichage des détails
print(f"{mon_chien.nom}, {mon_chien.age} ans, Race: {mon_chien.race}")
print(f"{mon_chat.nom}, {mon_chat.age} ans, Couleur: {mon_chat.couleur}")

# Appel des méthodes
mon_chien.faire_du_bruit()  # Affiche : Le chien aboie.
mon_chat.faire_du_bruit()    # Affiche : Le chat miaule.
```





[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-11"></a>
<br/>

---
## 11 - Polymorphisme en Python
---

*Comprendre et appliquer le polymorphisme en Programmation Orientée Objet avec Python, avec des explications approfondies, des analogies simples et des exemples clairs.*



11.1. [Introduction au polymorphisme](#partie-11-1) <br/>
11.2. [Pourquoi utiliser le polymorphisme ?](#partie-11-2) <br/>
11.3. [Le polymorphisme avec des méthodes](#partie-11-3) <br/>
11.4. [Le polymorphisme avec des classes et l'héritage](#partie-11-4) <br/>
11.5. [Le polymorphisme avec des fonctions et opérateurs](#partie-11-5) <br/>
11.6. [Le polymorphisme avec des interfaces (ABC)](#partie-11-6) <br/>
11.7. [Avantages du polymorphisme](#partie-11-7) <br/>
11.8. [Exercice pratique](#partie-11-8) <br/>
11.9. [Solution de l'exercice](#partie-11-9) <br/>
11.10. [Résumé et bonnes pratiques](#partie-11-10) <br/>


<a name="partie-11-1"></a>
<br/>

---
### 11.1 - Introduction au polymorphisme
---

#### Qu'est-ce que le polymorphisme ?

Le terme polymorphisme vient du grec *polymorphos* qui signifie "**plusieurs formes**". En **Programmation Orientée Objet (POO)**, cela signifie qu'une seule interface (méthode, fonction ou opérateur) peut se comporter de manière différente selon l'objet sur lequel elle est appliquée.



#### Une analogie pour comprendre

Imaginez un **interrupteur** :
- Un interrupteur dans une pièce allume une **ampoule**.
- Un autre interrupteur dans le salon allume un **ventilateur**.
- Un autre dans la cuisine allume un **micro-ondes**.

Bien que chaque interrupteur soit identique en apparence (même interface), ils contrôlent des **appareils différents** et donc, ont des **comportements différents**.

C'est exactement ce que fait le polymorphisme : **la même méthode** peut produire des résultats différents selon l'**objet** sur lequel elle est appelée.


#### Exemple simple en Python

```python
print(len("Python"))   # Affiche : 6 (taille de la chaîne)
print(len([1, 2, 3]))  # Affiche : 3 (nombre d'éléments dans la liste)
```

Ici :
- La fonction `len()` est identique, mais elle donne un résultat différent selon qu'on lui passe une chaîne ou une liste.
- **C'est du polymorphisme !**

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-11-2"></a>
<br/>

---
### 11.2 - Pourquoi utiliser le polymorphisme ? 
---

Le polymorphisme permet :
- **D'écrire du code plus générique** et réutilisable.
- **D'éviter la répétition** de code.
- **D'ajouter de nouvelles fonctionnalités** sans modifier le code existant.
- **De rendre le code flexible** : Une fonction ou méthode peut fonctionner avec plusieurs types d'objets.


#### Une autre analogie 
Imaginez un **port USB** sur un ordinateur :
- Vous pouvez brancher une **souris**, un **clavier**, une **clé USB** ou même un **téléphone**.
- L'ordinateur sait comment interagir avec chacun de ces appareils, même si vous utilisez le **même port**.

De la même manière, une fonction ou méthode Python peut interagir avec différents objets, en adaptant son comportement selon l'objet reçu.

[🔙 Retour à la table des matières](#table-des-matieres)


<a name="partie-11-3"></a>
<br/>

---
### 11.3 - Le polymorphisme avec des méthodes
---

En Python, différentes classes peuvent implémenter **la même méthode**, mais avec des **comportements distincts**.


#### Exemple 

```python
class Oiseau:
    def son(self):
        print("L'oiseau chante.")

class Chien:
    def son(self):
        print("Le chien aboie.")
```

### Utilisation du polymorphisme 

```python
def faire_son(animal):
    animal.son()

oiseau = Oiseau()
chien = Chien()

faire_son(oiseau)  # Affiche : L'oiseau chante.
faire_son(chien)   # Affiche : Le chien aboie.
```

> Ici, la fonction `faire_son()` est polymorphe : elle utilise la méthode `son()` de manière **différente** selon l'**objet** passé (un `Oiseau` ou un `Chien`).

[🔙 Retour à la table des matières](#table-des-matieres)

<a name="partie-11-4"></a>
<br/>

---
### 11.4 - Le polymorphisme avec des classes et l'héritage
---

L’héritage permet à une **classe fille** de **surcharger** une méthode de la **classe parente** pour l’adapter à ses besoins.

#### Exemple détaillé 

```python
class Forme:
    def aire(self):
        return "Méthode non implémentée"

class Carre(Forme):
    def __init__(self, cote):
        self.cote = cote

    def aire(self):
        return self.cote ** 2

class Cercle(Forme):
    def __init__(self, rayon):
        self.rayon = rayon

    def aire(self):
        return 3.14 * self.rayon ** 2
```

#### Utilisation du polymorphisme 
```python
formes = [Carre(4), Cercle(3)]

for forme in formes:
    print(f"Aire : {forme.aire()}")
```

#### Que se passe-t-il ici ?
- `Carre` et `Cercle` **héritent** de `Forme`, mais chacun a sa propre version de `aire()`.
- La **même méthode** (`aire()`) a des **comportements différents** selon l'objet sur lequel elle est appelée.
- Python sait **automatiquement** quelle version appeler !

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-11-5"></a>
<br/>

---
### 11.5 - Le polymorphisme avec des fonctions et opérateurs
---

Python permet aussi le polymorphisme avec des **fonctions** et même des **opérateurs**.


#### Exemple avec une fonction 

```python
def addition(a, b):
    return a + b

print(addition(5, 3))       # Affiche : 8
print(addition("Hello ", "World"))  # Affiche : Hello World
```

#### Exemple avec des opérateurs 

```python
print(5 + 3)        # Affiche : 8 (addition)
print("a" + "b")    # Affiche : ab (concaténation)
```

> L'**opérateur `+`** est polymorphe : il **ajoute des nombres** et **concatène des chaînes**.

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-11-6"></a>
<br/>

---
### 11.6 - Le polymorphisme avec des interfaces (ABC)
---

Une **interface** (ou **classe abstraite**) définit des **méthodes obligatoires** pour les classes qui en héritent. Python utilise le module `abc` pour cela.



#### Exemple avec `ABC` 
```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def faire_son(self):
        pass

class Chien(Animal):
    def faire_son(self):
        return "Aboie"

class Chat(Animal):
    def faire_son(self):
        return "Miaule"

animaux = [Chien(), Chat()]
for animal in animaux:
    print(animal.faire_son())
```

> L'interface `Animal` **force** les classes `Chien` et `Chat` à implémenter `faire_son()`.

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-11-7"></a>
<br/>

---
### 11.7 - Avantages du polymorphisme 
---

- **Flexibilité** : Le code peut fonctionner avec plusieurs types d'objets.
- **Réutilisation** : Moins de code redondant.
- **Extensibilité** : Ajoute de nouvelles classes sans modifier le code existant.
- **Lisibilité** : Le code est plus simple et intuitif.
- **Maintenance** : Le code est plus facile à entretenir et à faire évoluer.

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-11-8"></a>
<br/>

---
### 11.8 - Exercice pratique 
---

### Instructions 
11.8.1. Crée une classe `Instrument` avec une méthode `jouer()` vide.
11.8.2. Crée deux classes `Guitare` et `Piano` qui héritent de `Instrument` :
   - **`Guitare`** : la méthode `jouer()` affiche `"La guitare joue une mélodie."`
   - **`Piano`** : la méthode `jouer()` affiche `"Le piano joue une symphonie."`
11.8.3. Crée une fonction `concert()` qui prend un `instrument` et appelle sa méthode `jouer()`.


### Ce que tu dois faire 
- Crée des objets `Guitare` et `Piano`.
- Utilise la fonction `concert()` avec les deux objets.
- Affiche les sorties.

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-11-9"></a>
<br/>

---
### 11.9 - Solution de l'exercice 
---

```python
class Instrument:
    def jouer(self):
        pass

class Guitare(Instrument):
    def jouer(self):
        print("La guitare joue une mélodie.")

class Piano(Instrument):
    def jouer(self):
        print("Le piano joue une symphonie.")

def concert(instrument):
    instrument.jouer()

guitare = Guitare()
piano = Piano()

concert(guitare)  # Affiche : La guitare joue une mélodie.
concert(piano)    # Affiche : Le piano joue une symphonie.
```

[🔙 Retour à la table des matières](#table-des-matieres)
<a name="partie-11-10"></a>
<br/>


---
### 11.10 - Résumé et bonnes pratiques 
---

- Le **polymorphisme** permet d'écrire du **code flexible et réutilisable**.
- Utilisez l'**héritage** pour surcharger des méthodes.
- Les **interfaces (ABC)** assurent qu'une méthode sera toujours définie.
- **Favorisez le polymorphisme** pour rendre votre code plus maintenable.

[🔙 Retour à la table des matières](#table-des-matieres)











