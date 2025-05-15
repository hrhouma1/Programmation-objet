#  CORRECTION  – EXAMEN SUR LES CLASSES ABSTRAITES, L’HÉRITAGE ET LE POLYMORPHISME EN PYTHON



## PARTIE 1 : QCM, VRAI/FAUX, QUESTIONS OUVERTES




# **Question 1.**
Que permet le module `abc` en Python ?
- A. Créer des classes statiques
- B. Implémenter des interfaces
- C. Définir des classes abstraites
- D. Éviter l'héritage multiple




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


<br/>
<br/>




# **Question 2.**

Quel mot-clé est utilisé pour déclarer une méthode abstraite ?

* A. `defabstract`
* B. `virtualmethod`
* C. `@abstractmethod`
* D. `@abstract`

---

# **Question 2 : Quel mot-clé est utilisé pour déclarer une méthode abstraite ?**

* **Réponse correcte : C. `@abstractmethod`**

**Explication complète :**
Il s’agit d’un **décorateur** fourni par le module `abc`. Lorsqu’il est appliqué à une méthode dans une classe dérivée de `ABC`, il indique que cette méthode **doit impérativement être redéfinie** dans toute sous-classe concrète.

**Exemple :**

```python
from abc import ABC, abstractmethod

class Machine(ABC):
    @abstractmethod
    def executer(self):
        pass
```

**À retenir :**

* Le décorateur `@abstractmethod` est **obligatoire** pour marquer une méthode comme abstraite.
* Les propositions A, B et D sont incorrectes : ce ne sont **pas des mots-clés valides en Python**.

---

# **Question 3.**

Une classe abstraite peut :

* A. Être instanciée directement
* B. Contenir des méthodes concrètes
* C. Avoir uniquement des attributs privés
* D. Contenir uniquement des méthodes abstraites

---

# **Question 3 : Une classe abstraite peut :**

* **Réponse correcte : B. Contenir des méthodes concrètes**

**Explication complète :**
Une classe abstraite en Python peut contenir :

* Des **méthodes abstraites** (sans implémentation, marquées avec `@abstractmethod`)
* Des **méthodes concrètes** (avec un corps de méthode)

Cela permet à la classe abstraite de **fournir des comportements par défaut** tout en **imposant** certaines méthodes à ses sous-classes.

**Exemple :**

```python
from abc import ABC, abstractmethod

class Vehicule(ABC):
    def arreter(self):
        print("Arrêt du véhicule.")

    @abstractmethod
    def demarrer(self):
        pass
```

**Erreur fréquente :**
Croire qu’une classe abstraite ne peut contenir que des méthodes abstraites. En réalité, elle peut offrir des fonctionnalités de base communes à toutes ses sous-classes.

---

# **Question 4.**

Qu'arrive-t-il si une sous-classe ne redéfinit pas toutes les méthodes abstraites ?

* A. Elle hérite normalement
* B. Elle est instanciable
* C. Elle devient elle-même abstraite
* D. Le programme plante immédiatement

---

# **Question 4 : Si une sous-classe ne redéfinit pas toutes les méthodes abstraites ?**

* **Réponse correcte : C. Elle devient elle-même abstraite**

**Explication complète :**
Lorsqu'une sous-classe hérite d’une classe abstraite mais **n’implémente pas toutes les méthodes abstraites**, elle **reste abstraite**.
Cela signifie qu’elle **ne pourra pas être instanciée**.

**Exemple illustratif :**

```python
from abc import ABC, abstractmethod

class Capteur(ABC):
    @abstractmethod
    def mesurer(self):
        pass

class Thermometre(Capteur):
    pass  # aucune redéfinition

# Instanciation interdite :
t = Thermometre()  # Provoque une TypeError
```

**Règle à retenir :**
Une sous-classe est **obligée de redéfinir toutes les méthodes abstraites** pour devenir instanciable. Sinon, elle devient à son tour abstraite.


<br/>
<br/>






# **Question 5.**

Quel est le rôle du polymorphisme ?

* A. Empêcher l’héritage
* B. Permettre à différentes classes d’avoir une méthode du même nom mais avec des comportements différents
* C. Masquer les attributs
* D. Créer des objets statiques

---

# **Question 5 : Rôle du polymorphisme ?**

* **Réponse correcte : B. Permettre à différentes classes d’avoir une méthode du même nom mais avec des comportements différents**

**Explication complète :**
Le **polymorphisme** permet d’utiliser une **même méthode** (même nom) sur plusieurs types d’objets, chaque objet pouvant avoir une implémentation différente.

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

faire_parler(Chien())  # Aboie
faire_parler(Chat())   # Miaule
```

**À retenir :**

* Le polymorphisme évite les chaînes de conditions `if type(...)` en permettant un comportement automatique basé sur le type réel de l’objet.
* Il est central pour écrire du code **générique**, **extensible** et **réutilisable**.

---

# **Question 6.**

Quelle est la sortie du code suivant ?

```python
class Animal:
    def parler(self):
        print("L'animal fait un bruit.")

class Chien(Animal):
    def parler(self):
        print("Le chien aboie.")

a = Chien()
a.parler()
```

* A. L'animal fait un bruit.
* B. Le chien aboie.
* C. Erreur d'exécution
* D. Rien ne s’affiche

---

# **Question 6 : Résultat du code**

* **Réponse correcte : B. Le chien aboie.**

**Explication complète :**
La classe `Chien` redéfinit la méthode `parler()` héritée de `Animal`. Lorsqu’on instancie `Chien` et qu’on appelle `parler()`, c’est la **méthode redéfinie** dans `Chien` qui est exécutée.

**Règle à retenir :**
En Python, la méthode appelée dépend du **type réel** de l’objet, pas du type de la variable.

---

# **Question 7.**

Parmi les éléments suivants, lesquels sont VRAIS ? (choix multiples possibles)

* A. `ABC` signifie Abstract Base Class
* B. On ne peut pas créer d'objet d'une classe abstraite
* C. Le décorateur `@abstractmethod` s’utilise uniquement dans une classe enfant
* D. Une classe peut hériter de plusieurs classes abstraites

---

# **Question 7 : Choix multiples**

* **Réponses correctes : A, B, D**

**Explications :**

* A. ✅ `ABC` est l’acronyme de **Abstract Base Class**, utilisé comme base pour créer des classes abstraites.
* B. ✅ Une classe abstraite ne peut **pas être instanciée** si elle contient une méthode abstraite non redéfinie.
* C. ❌ Faux : `@abstractmethod` s’utilise dans la **classe de base**, jamais dans la sous-classe.
* D. ✅ Python autorise l’**héritage multiple**, y compris entre plusieurs classes abstraites.

---

# **Question 8.**

Quel est le type de relation entre une classe parent et une classe enfant ?

* A. Association
* B. Agrégation
* C. Composition
* D. Héritage

---

# **Question 8 : Type de relation entre parent et enfant**

* **Réponse correcte : D. Héritage**

**Explication complète :**
L’héritage est une relation entre classes où une classe enfant **hérite** des attributs et méthodes d’une classe parent.
C’est une relation **"est-un"**.
Exemple : un `Chien` **est un** `Animal`.

**Les autres options relèvent de la modélisation UML :**

* **Association** : relation de collaboration
* **Agrégation** : relation faible "fait partie de"
* **Composition** : relation forte de dépendance

---

# **Question 9.**

Une méthode redéfinie dans une sous-classe :

* A. Supprime la méthode parent
* B. La remplace dans les instances de la sous-classe
* C. Inhibe toutes les méthodes abstraites
* D. Est appelée uniquement via `super()`

---

# **Question 9 : Méthode redéfinie**

* **Réponse correcte : B. La remplace dans les instances de la sous-classe**

**Explication complète :**
Quand une méthode est redéfinie dans une sous-classe, elle **masque** (ou écrase) celle de la classe parente **uniquement pour les instances de cette sous-classe**.

**Exemple :**

```python
class Parent:
    def dire_bonjour(self):
        print("Bonjour du parent")

class Enfant(Parent):
    def dire_bonjour(self):
        print("Bonjour de l’enfant")

e = Enfant()
e.dire_bonjour()  # Bonjour de l’enfant
```

---

# **Question 10.**

Le polymorphisme permet d’appeler une méthode :

* A. De manière statique
* B. En ignorant l’objet cible
* C. En fonction du type réel de l’objet
* D. En fonction du type de la variable

---

# **Question 10 : Appel de méthode et polymorphisme**

* **Réponse correcte : C. En fonction du type réel de l’objet**

**Explication complète :**
Même si on utilise une variable typée comme `Animal`, si on y stocke un objet de type `Chien`, alors c’est la méthode de `Chien` qui est exécutée.

**Exemple :**

```python
animal = Chien()  # Chien hérite de Animal
animal.parler()   # C'est parler() de Chien qui est exécuté
```

**Règle :**
En Python (comme en Java, C#), le **polymorphisme dynamique** est basé sur le **type réel** de l'objet, pas celui de la référence.






<br/>
<br/>



# Partie 2 - Questions ouvertes / Vrai-Faux / Codes à analyser



# **Question 11.**

Vrai ou Faux : Une classe qui hérite d'une classe abstraite peut être instanciée même si elle n’implémente pas toutes les méthodes abstraites.

---

# **Question 11 : Vrai ou Faux – Classe incomplète instanciable ?**

* **Réponse : Faux**

**Explication complète :**
Une classe qui hérite d’une classe abstraite **et** qui ne redéfinit pas toutes ses méthodes abstraites **reste abstraite** elle-même. Par conséquent, elle **ne peut pas être instanciée**.

**Règle à retenir :**
Tant qu'une méthode abstraite n'est pas redéfinie dans une classe, cette classe est abstraite et Python lèvera une `TypeError` à l’instanciation.

---

# **Question 12.**

Vrai ou Faux : `super()` permet d'appeler les méthodes de la classe parente même dans une classe qui hérite.

---

# **Question 12 : Vrai ou Faux – Utilité de `super()`**

* **Réponse : Vrai**

**Explication complète :**
La fonction `super()` permet d’accéder à une méthode de la classe parente depuis une sous-classe. Elle est très utile dans le cas de redéfinitions, lorsqu’on souhaite **conserver une partie du comportement de la classe parente**, puis le compléter.

**Exemple :**

```python
class Parent:
    def afficher(self):
        print("Parent")

class Enfant(Parent):
    def afficher(self):
        super().afficher()
        print("Enfant")

e = Enfant()
e.afficher()
```

---

# **Question 13.**

Donnez un exemple de situation réelle où le polymorphisme est utile dans une application logicielle.

---

# **Question 13 : Exemple réel de polymorphisme**

**Réponse attendue :**
Dans une application de gestion des paiements, chaque classe (`CarteCredit`, `PayPal`, `Cryptomonnaie`) a une méthode `payer()`. Grâce au polymorphisme, on peut faire :

```python
for moyen in liste_moyens_paiement:
    moyen.payer()
```

Peu importe le type de chaque objet, la méthode correcte sera appelée.

---

# **Question 14.**

Complétez ce code pour créer une méthode abstraite nommée `analyser()` :

```python
from abc import ABC, abstractmethod

class Capteur(ABC):
    # Votre réponse ici
```

---

# **Question 14 : Compléter avec méthode abstraite**

```python
from abc import ABC, abstractmethod

class Capteur(ABC):
    @abstractmethod
    def analyser(self):
        pass
```

**Règle :**
On doit utiliser `@abstractmethod` sur une méthode d’une classe héritant d’`ABC` pour forcer sa redéfinition.

---

# **Question 15.**

Quel est l'intérêt d’utiliser une classe abstraite au lieu d’une classe classique ?

---

# **Question 15 : Intérêt d’une classe abstraite**

**Réponse attendue :**
Une classe abstraite permet de **définir une interface commune** à toutes les sous-classes et de **forcer l’implémentation de certaines méthodes essentielles**, assurant ainsi la cohérence du système.

---

# **Question 16.**

Expliquez en une phrase ce qu’est l’héritage en Python.

---

# **Question 16 : Héritage en Python**

**Réponse attendue :**
L’héritage permet à une classe de **réutiliser, redéfinir ou compléter** les attributs et méthodes d’une autre classe.

---

# **Question 17.**

Corrigez le code suivant pour qu’il fonctionne sans erreur :

```python
from abc import ABC

class Machine(ABC):
    def demarrer(self):
        pass

class Imprimante(Machine):
    pass

i = Imprimante()
i.demarrer()
```

---

# **Question 17 : Corriger le code**

**Code corrigé (version abstraite réelle) :**

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

**Explication :**
Le problème du code initial est qu’il déclarait `Machine` comme classe abstraite sans méthode abstraite réelle. Pour forcer la redéfinition, on ajoute `@abstractmethod`.

---

# **Question 18.**

Vrai ou Faux : Une classe peut hériter d'une classe abstraite tout en restant elle-même abstraite.

---

# **Question 18 : Vrai ou Faux – Classe abstraite héritée**

* **Réponse : Vrai**

**Explication complète :**
Une classe peut hériter d'une classe abstraite sans implémenter toutes les méthodes abstraites. Dans ce cas, elle reste abstraite et ne pourra pas être instanciée.

---

# **Question 19.**

Donnez une définition simple du terme **polymorphisme** en programmation orientée objet.

---

# **Question 19 : Définition du polymorphisme**

**Réponse attendue :**
Le polymorphisme est la capacité d’utiliser **la même méthode sur des objets de types différents**, chaque type ayant sa propre implémentation de cette méthode.

---

# **Question 20.**

Expliquez pourquoi le polymorphisme est utile dans un programme utilisant des listes d’objets de types différents.

---

# **Question 20 : Pourquoi le polymorphisme est utile**

**Réponse attendue :**
Il permet d’**écrire un code générique** qui traite tous les objets de manière uniforme, sans avoir à tester leur type, rendant le code plus propre, flexible et évolutif.

---

## PARTIE 2 – Conception de classe abstraite

---

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

---

# Classe 1 : `ThermometreNumerique`

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

---

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

---

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

---

# Document explicatif à rendre (`explication.txt`)

```
Concept choisi : Dispositif de mesure

Pourquoi : Il représente une abstraction réaliste utilisée dans le domaine médical, environnemental ou industriel. Il impose une interface commune à tous les capteurs.

Raisonnement : On impose trois méthodes obligatoires. Chaque classe implémente ces méthodes selon sa logique métier. Le polymorphisme permet de les manipuler toutes de manière uniforme.

Objectif pédagogique : Montrer comment un modèle bien abstrait permet de structurer proprement une application complexe avec des composants variés mais compatibles.
```





















