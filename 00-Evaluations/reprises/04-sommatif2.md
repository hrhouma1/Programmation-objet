# Partie 1


### **QCM / Choix Multiples**

**Question 1.**
Que permet le module `abc` en Python ?
A. Créer des classes statiques
B. Implémenter des interfaces
C. Définir des classes abstraites
D. Éviter l'héritage multiple

**Question 2.**
Quel mot-clé est utilisé pour déclarer une méthode abstraite ?
A. `defabstract`
B. `virtualmethod`
C. `@abstractmethod`
D. `@abstract`

**Question 3.**
Une classe abstraite peut :
A. Être instanciée directement
B. Contenir des méthodes concrètes
C. Avoir uniquement des attributs privés
D. Contenir uniquement des méthodes abstraites

**Question 4.**
Qu'arrive-t-il si une sous-classe ne redéfinit pas toutes les méthodes abstraites ?
A. Elle hérite normalement
B. Elle est instanciable
C. Elle devient elle-même abstraite
D. Le programme plante immédiatement

**Question 5.**
Quel est le rôle du polymorphisme ?
A. Empêcher l’héritage
B. Permettre à différentes classes d’avoir une méthode du même nom mais avec des comportements différents
C. Masquer les attributs
D. Créer des objets statiques

**Question 6.**
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

A. L'animal fait un bruit.
B. Le chien aboie.
C. Erreur d'exécution
D. Rien ne s’affiche

**Question 7.**
Parmi les éléments suivants, lesquels sont VRAIS ? (choix multiples possibles)
A. `ABC` signifie Abstract Base Class
B. On ne peut pas créer d'objet d'une classe abstraite
C. Le décorateur `@abstractmethod` s’utilise uniquement dans une classe enfant
D. Une classe peut hériter de plusieurs classes abstraites

**Question 8.**
Quel est le type de relation entre une classe parent et une classe enfant ?
A. Association
B. Agrégation
C. Composition
D. Héritage

**Question 9.**
Une méthode redéfinie dans une sous-classe :
A. Supprime la méthode parent
B. La remplace dans les instances de la sous-classe
C. Inhibe toutes les méthodes abstraites
D. Est appelée uniquement via `super()`

**Question 10.**
Le polymorphisme permet d’appeler une méthode :
A. De manière statique
B. En ignorant l’objet cible
C. En fonction du type réel de l’objet
D. En fonction du type de la variable



### **Questions ouvertes / Vrai-Faux / Codes à analyser**

**Question 11.**
Vrai ou Faux : Une classe qui hérite d'une classe abstraite peut être instanciée même si elle n’implémente pas toutes les méthodes abstraites.

**Question 12.**
Vrai ou Faux : `super()` permet d'appeler les méthodes de la classe parente même dans une classe qui hérite.

**Question 13.**
Donnez un exemple de situation réelle où le polymorphisme est utile dans une application logicielle.

**Question 14.**
Complétez ce code pour créer une méthode abstraite nommée `analyser()` :

```python
from abc import ABC, abstractmethod

class Capteur(ABC):
    # Votre réponse ici
```

**Question 15.**
Quel est l'intérêt d’utiliser une classe abstraite au lieu d’une classe classique ?

**Question 16.**
Expliquez en une phrase ce qu’est l’héritage en Python.

**Question 17.**
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

**Question 18.**
Vrai ou Faux : Une classe peut hériter d'une classe abstraite tout en restant elle-même abstraite.

**Question 19.**
Donnez une définition simple du terme **polymorphisme** en programmation orientée objet.

**Question 20.**
Expliquez pourquoi le polymorphisme est utile dans un programme utilisant des listes d’objets de types différents.


<br/>
<br/>


# Partie 2 : Conception d'une Classe Abstraite pour un Dispositif de Mesure



1. **Proposez une classe abstraite de votre choix** représentant un **dispositif de mesure** dans un contexte scientifique, médical, environnemental ou industriel (par exemple : `Thermometre`, `CapteurDePression`, `AnalyseurDeGaz`, etc.).
2. Votre classe abstraite doit contenir **au minimum trois méthodes abstraites** listées dans le tableau ci-dessous :

| Méthode attendue       | Description                              |
| ---------------------- | ---------------------------------------- |
| `demarrer_mesure()`    | Lance la procédure de mesure             |
| `arreter_mesure()`     | Termine ou interrompt la mesure          |
| `afficher_resultats()` | Affiche ou restitue les données mesurées |

3. Créez **au moins deux classes concrètes** héritant de cette classe abstraite et implémentant toutes les méthodes de manière spécifique à chaque dispositif.
4. **Testez votre code** en instanciant vos classes concrètes et en appelant leurs méthodes.



# **Contraintes supplémentaires :**

* Vous devez remettre un fichier `.py` contenant **votre propre conception de la classe abstraite et ses deux implémentations concrètes**.
* **Aucun code ne doit être partagé entre étudiants. Toute similitude injustifiée sera considérée comme du plagiat.**
* Soyez original, pertinent et rigoureux dans la structure de votre code.

---

### **À Rendre :**

* Le fichier `.py` complet.
* Un court **document texte** expliquant le concept choisi, les raisons de ce choix et la logique de votre modélisation.

