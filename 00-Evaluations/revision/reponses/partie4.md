#  CORRECTION  – EXAMEN SUR LES CLASSES ABSTRAITES, L’HÉRITAGE ET LE POLYMORPHISME EN PYTHON



## PARTIE 1 : QCM, VRAI/FAUX, QUESTIONS OUVERTES




**Question 1.**
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




**Question 2.**
Quel mot-clé est utilisé pour déclarer une méthode abstraite ?

- A. `defabstract`
- B. `virtualmethod`
- C. `@abstractmethod`
- D. `@abstract`





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







**Question 3.**
Une classe abstraite peut :
- A. Être instanciée directement
- B. Contenir des méthodes concrètes
- C. Avoir uniquement des attributs privés
- D. Contenir uniquement des méthodes abstraites




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






**Question 4.**
Qu'arrive-t-il si une sous-classe ne redéfinit pas toutes les méthodes abstraites ?
- A. Elle hérite normalement
- B. Elle est instanciable
- C. Elle devient elle-même abstraite
- D. Le programme plante immédiatement



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





**Question 5.**
Quel est le rôle du polymorphisme ?
- A. Empêcher l’héritage
- B. Permettre à différentes classes d’avoir une méthode du même nom mais avec des comportements différents
- C. Masquer les attributs
- D. Créer des objets statiques

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
- A.parler()
```

- A. L'animal fait un bruit.
- B. Le chien aboie.
- C. Erreur d'exécution
- D. Rien ne s’affiche



# **Question 6 : Résultat du code**

* **Réponse correcte : B. Le chien aboie.**

**Pourquoi ?**
La méthode `parler()` a été redéfinie dans `Chien`. L’appel se fait sur une instance de `Chien`, donc c’est sa version qui est exécutée.












**Question 7.**
Parmi les éléments suivants, lesquels sont VRAIS ? (choix multiples possibles)
- A. `ABC` signifie Abstract Base Class
- B. On ne peut pas créer d'objet d'une classe abstraite
- C. Le décorateur `@abstractmethod` s’utilise uniquement dans une classe enfant
- D. Une classe peut hériter de plusieurs classes abstraites


# **Question 7 : Choix multiples**

* **Réponses correctes : A, B, D**

**Explications :**

* A. ✅ Vrai : ABC = Abstract Base Class
* B. ✅ Vrai : Une classe abstraite ne peut pas être instanciée
* C. ❌ Faux : `@abstractmethod` est utilisé **dans la classe de base**, pas dans les enfants
* D. ✅ Vrai : Python accepte l’héritage multiple, y compris entre classes abstraites














**Question 8.**
Quel est le type de relation entre une classe parent et une classe enfant ?
- A. Association
- B. Agrégation
- C. Composition
- D. Héritage

# **Question 8 : Type de relation entre parent et enfant**

* **Réponse correcte : D. Héritage**

**Explication :**
Il s’agit d’une relation “est-un” (ex : un Chien **est un** Animal).
Ce n’est ni une association, ni une agrégation ou composition (qui sont utilisées en UML pour la structuration d’objets différents).










**Question 9.**
Une méthode redéfinie dans une sous-classe :
- A. Supprime la méthode parent
- B. La remplace dans les instances de la sous-classe
- C. Inhibe toutes les méthodes abstraites
- D. Est appelée uniquement via `super()`



# **Question 9 : Méthode redéfinie**

* **Réponse correcte : B. La remplace dans les instances de la sous-classe**

**Explication :**
Quand une sous-classe redéfinit une méthode du parent, elle la **masque** pour ses propres instances.












**Question 10.**
Le polymorphisme permet d’appeler une méthode :
- A. De manière statique
- B. En ignorant l’objet cible
- C. En fonction du type réel de l’objet
- D. En fonction du type de la variable






# **Question 10 : Appel de méthode et polymorphisme**

* **Réponse correcte : C. En fonction du type réel de l’objet**

**Explication :**
Même si une variable est typée comme `Vehicule`, si l’objet réel est un `Moto`, c’est la méthode de `Moto` qui est appelée.





### **Questions ouvertes / Vrai-Faux / Codes à analyser**

**Question 11.**
Vrai ou Faux : Une classe qui hérite d'une classe abstraite peut être instanciée même si elle n’implémente pas toutes les méthodes abstraites.



# **Question 11 : Vrai ou Faux – Classe incomplète instanciable ?**

* **Réponse : Faux**

**Règle :**
Une classe qui n’implémente pas toutes les méthodes abstraites reste abstraite et ne peut pas être instanciée.











**Question 12.**
Vrai ou Faux : `super()` permet d'appeler les méthodes de la classe parente même dans une classe qui hérite.


  
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



**Question 13.**
Donnez un exemple de situation réelle où le polymorphisme est utile dans une application logicielle.

**Question 14.**
Complétez ce code pour créer une méthode abstraite nommée `analyser()` :

```python
from abc import ABC, abstractmethod

class Capteur(ABC):
    # Votre réponse ici
```

# **Question 14 : Compléter avec méthode abstraite**

```python
from abc import ABC, abstractmethod

class Capteur(ABC):
    @abstractmethod
    def analyser(self):
        pass
```





**Question 15.**
Quel est l'intérêt d’utiliser une classe abstraite au lieu d’une classe classique ?




# **Question 15 : Intérêt d’une classe abstraite**

**Réponse attendue :**

Elle permet d’**imposer une structure** dans une hiérarchie de classes et de s’assurer que **certaines méthodes essentielles seront bien définies**.





**Question 16.**
Expliquez en une phrase ce qu’est l’héritage en Python.


# **Question 16 : Héritage en Python**

**Réponse attendue :**

L’héritage permet à une classe d’**hériter les attributs et méthodes** d’une autre classe, pour les réutiliser ou les spécialiser.




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




**Question 18.**
Vrai ou Faux : Une classe peut hériter d'une classe abstraite tout en restant elle-même abstraite.



**Question 19.**
Donnez une définition simple du terme **polymorphisme** en programmation orientée objet.



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


