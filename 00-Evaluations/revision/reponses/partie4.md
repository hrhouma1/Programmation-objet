#  CORRECTION EXHAUSTIVE – EXAMEN SUR LES CLASSES ABSTRAITES, L’HÉRITAGE ET LE POLYMORPHISME EN PYTHON



# PARTIE 1 : QCM, VRAI/FAUX, QUESTIONS OUVERTES



# **Question 1 : Que permet le module `abc` en Python ?**

* **Réponse correcte : C. Définir des classes abstraites**

**Explication complète :**

Le module `abc` signifie **Abstract Base Classes**. Il est utilisé pour créer des **classes abstraites**, c’est-à-dire des classes qui ne peuvent **pas être instanciées directement**, mais qui **forcent les sous-classes** à implémenter certaines méthodes.

**Syntaxe typique :**

```python
from abc import ABC, abstractmethod

class Vehicule(ABC):
    @abstractmethod
    def demarrer(self):
        pass
```

**Règle à retenir :**
Une classe qui hérite de `ABC` et qui contient une méthode décorée avec `@abstractmethod` devient une classe abstraite.

**Erreur fréquente :**
Confondre le mot *interface* (terme général ou Java) avec `abc` en Python. En Python, on parle plutôt de **classe abstraite** que d’interface.



# **Question 2 : Quel mot-clé est utilisé pour déclarer une méthode abstraite ?**

* **Réponse correcte : C. `@abstractmethod`**

**Explication complète :**
C’est un **décorateur** qui s’applique à une méthode pour dire que **toute classe qui hérite** devra redéfinir cette méthode.

**Exemple :**

```python
class Machine(ABC):
    @abstractmethod
    def executer(self):
        pass
```

**À retenir :**
On n’utilise jamais `@abstract`, `defabstract` ou `virtualmethod` en Python.



# **Question 3 : Une classe abstraite peut :**

* **Réponse correcte : B. Contenir des méthodes concrètes**

**Explication complète :**
Une classe abstraite n’est pas obligée d’avoir uniquement des méthodes abstraites. Elle peut contenir :

* Des méthodes abstraites (non définies)
* Des méthodes concrètes (avec un corps de méthode)

**Exemple :**

```python
class Vehicule(ABC):
    def arreter(self):
        print("Véhicule arrêté.")
    
    @abstractmethod
    def demarrer(self):
        pass
```

**Erreur fréquente :**
Croire qu’une classe abstraite = aucune implémentation. En réalité, elle peut contenir du code.



# **Question 4 : Si une sous-classe ne redéfinit pas toutes les méthodes abstraites ?**

* **Réponse correcte : C. Elle devient elle-même abstraite**

**Explication complète :**
Une sous-classe **incomplète** (qui n’implémente pas toutes les méthodes abstraites) devient automatiquement abstraite et **ne peut pas être instanciée**.

**Exemple :**

```python
class Capteur(ABC):
    @abstractmethod
    def mesurer(self):
        pass

class Thermometre(Capteur):
    pass  # pas d'implémentation

t = Thermometre()  # Erreur !
```



# **Question 5 : Rôle du polymorphisme ?**

* **Réponse correcte : B. Permettre à différentes classes d’avoir une méthode du même nom mais avec des comportements différents**

**Explication complète :**

Le **polymorphisme** permet de manipuler des objets de classes différentes avec une **interface commune**.

**Exemple classique :**

```python
class Chien:
    def parler(self):
        print("Aboie")

class Chat:
    def parler(self):
        print("Miaule")

def faire_parler(animal):
    animal.parler()

faire_parler(Chien())
faire_parler(Chat())
```

**Sortie :**

```
Aboie
Miaule
```

**À retenir :**

* Même méthode → plusieurs comportements
* Très utilisé dans les boucles, collections, pipelines, etc.



# **Question 6 : Résultat du code**

* **Réponse correcte : B. Le chien aboie.**

**Pourquoi ?**
La méthode `parler()` a été redéfinie dans `Chien`. L’appel se fait sur une instance de `Chien`, donc c’est sa version qui est exécutée.



# **Question 7 : Choix multiples**

* **Réponses correctes : A, B, D**

**Explications :**

* A. ✅ Vrai : ABC = Abstract Base Class
* B. ✅ Vrai : Une classe abstraite ne peut pas être instanciée
* C. ❌ Faux : `@abstractmethod` est utilisé **dans la classe de base**, pas dans les enfants
* D. ✅ Vrai : Python accepte l’héritage multiple, y compris entre classes abstraites



# **Question 8 : Type de relation entre parent et enfant**

* **Réponse correcte : D. Héritage**

**Explication :**
Il s’agit d’une relation “est-un” (ex : un Chien **est un** Animal).
Ce n’est ni une association, ni une agrégation ou composition (qui sont utilisées en UML pour la structuration d’objets différents).



# **Question 9 : Méthode redéfinie**

* **Réponse correcte : B. La remplace dans les instances de la sous-classe**

**Explication :**
Quand une sous-classe redéfinit une méthode du parent, elle la **masque** pour ses propres instances.



# **Question 10 : Appel de méthode et polymorphisme**

* **Réponse correcte : C. En fonction du type réel de l’objet**

**Explication :**
Même si une variable est typée comme `Vehicule`, si l’objet réel est un `Moto`, c’est la méthode de `Moto` qui est appelée.



# **Question 11 : Vrai ou Faux – Classe incomplète instanciable ?**

* **Réponse : Faux**

**Règle :**
Une classe qui n’implémente pas toutes les méthodes abstraites reste abstraite et ne peut pas être instanciée.



# **Question 12 : Vrai ou Faux – Utilité de `super()`**

* **Réponse : Vrai**

**Explication :**
`super()` permet d’appeler une méthode de la classe parente, très utile pour compléter ou enrichir un comportement sans le réécrire complètement.



# **Question 13 : Exemple réel de polymorphisme**

**Exemple attendu :**

Dans un système de facturation, chaque type de client (`ClientIndividuel`, `ClientEntreprise`) a une méthode `calculer_remise()`. Grâce au polymorphisme, on peut faire :

```python
for client in liste_clients:
    print(client.calculer_remise())
```

Sans se soucier du type concret de `client`.



# **Question 14 : Compléter avec méthode abstraite**

```python
from abc import ABC, abstractmethod

class Capteur(ABC):
    @abstractmethod
    def analyser(self):
        pass
```


# **Question 15 : Intérêt d’une classe abstraite**

**Réponse attendue :**

Elle permet d’**imposer une structure** dans une hiérarchie de classes et de s’assurer que **certaines méthodes essentielles seront bien définies**.



# **Question 16 : Héritage en Python**

**Réponse attendue :**

L’héritage permet à une classe d’**hériter les attributs et méthodes** d’une autre classe, pour les réutiliser ou les spécialiser.



# **Question 17 : Corriger le code**

**Code corrigé :**

```python
from abc import ABC, abstractmethod

class Machine(ABC):
    @abstractmethod
    def demarrer(self):
        pass

class Imprimante(Machine):
    def demarrer(self):
        print("Imprimante démarrée")

i = Imprimante()
i.demarrer()
```



# **Question 18 : Vrai ou Faux – Classe abstraite héritée**

* **Réponse : Vrai**

Une classe peut hériter d’une classe abstraite et rester abstraite si elle ne complète pas toutes les méthodes.



# **Question 19 : Définition du polymorphisme**

**Définition attendue :**

Le polymorphisme permet d’utiliser une **même méthode** sur des objets de types différents, chaque objet ayant un comportement spécifique.



# **Question 20 : Pourquoi le polymorphisme est utile**

**Réponse attendue :**

Il permet de **traiter de manière uniforme** des objets de types différents dans des structures comme des listes, sans écrire de code spécifique pour chaque type.



## PARTIE 2 – Conception de classe abstraite



## Exemple de classe abstraite : `DispositifDeMesure`

```python
from abc import ABC, abstractmethod

class DispositifDeMesure(ABC):
    @abstractmethod
    def demarrer_mesure(self):
        pass

    @abstractmethod
    def arreter_mesure(self):
        pass

    @abstractmethod
    def afficher_resultats(self):
        pass
```



#  Classe 1 : `ThermometreNumerique`

```python
class ThermometreNumerique(DispositifDeMesure):
    def __init__(self):
        self.temperature = None

    def demarrer_mesure(self):
        self.temperature = 36.9
        print("Thermomètre en cours de mesure...")

    def arreter_mesure(self):
        print("Mesure arrêtée.")

    def afficher_resultats(self):
        print(f"Température mesurée : {self.temperature}°C")
```



# Classe 2 : `AnalyseurDeGaz`

```python
class AnalyseurDeGaz(DispositifDeMesure):
    def __init__(self):
        self.gaz = {}

    def demarrer_mesure(self):
        print("Début de l’analyse des gaz...")
        self.gaz = {"CO2": 0.04, "O2": 20.9, "N2": 78.0}

    def arreter_mesure(self):
        print("Analyse terminée.")

    def afficher_resultats(self):
        for nom, valeur in self.gaz.items():
            print(f"{nom} : {valeur}%")
```



# Test final

```python
if __name__ == "__main__":
    t = ThermometreNumerique()
    t.demarrer_mesure()
    t.arreter_mesure()
    t.afficher_resultats()

    print("")

    a = AnalyseurDeGaz()
    a.demarrer_mesure()
    a.arreter_mesure()
    a.afficher_resultats()
```


# Document explicatif à rendre (`explication.txt`)

```
Concept choisi : Dispositif de mesure

Pourquoi : Le concept est très présent dans les domaines scientifiques et industriels. Il permet de modéliser des appareils qui effectuent des mesures selon un protocole commun.

Raisonnement : On impose un contrat avec trois méthodes essentielles : démarrer la mesure, l’arrêter et afficher les résultats. Chaque sous-classe représente un appareil spécifique et fournit sa propre implémentation.

Objectif pédagogique : Montrer l’utilité des classes abstraites pour unifier les comportements et exploiter le polymorphisme dans les systèmes complexes.
```


