# Exercice : Analyse et correction de code Python orienté objet

# Énoncé

Voici un extrait de code censé définir une classe `Patient` héritée d'une classe abstraite.
Le but est de repérer toutes les erreurs de syntaxe ou de logique présentes dans ce code.

# 1 -  Code initial

```python
from abc import ABC, abstractmethod, abstractproperty

class Patient(ABC):
 def __init__(self, nom:str, prenom:str, age:int, numero_dossier:str, diagnostic:str):
 self.nom=nom
 self.prenom=prenom
 self.age=age
 self.numero_dossier=numero_dossier
 self.diagnostic=diagnostic

 @setter
 @property
 def set_age(self):
 if self.age<0:
 print("Erreur! l'âge ne peut pas être négatif!")
 new_age=input(int("entrez un nouvel age:"))
 self.age=new_age

 def traiter(self):
 pass

 def __str__(self):
 return (f" Fiche Patient\n "
 f"Nom : {self.nom}\n"
 f"Prenom : {self.prenom}\n"
 f"Âge : {self.age}\n"
 f"Dossier : {self.numero_diagnostic}\n"
 f"Diagnostic : {self.numero_diagnostic}")
```



# 2 - Questions

1. Relevez toutes les erreurs de **syntaxe**, **indentation**, **nom d’attribut** ou **logique**.
2. Expliquez brièvement chaque erreur.
3. Proposez une **version corrigée** du code.



# 3 - Correction attendue

### 1. Liste des erreurs

| Ligne               | Erreur                          | Explication                                                                            |
| ------------------- | ------------------------------- | -------------------------------------------------------------------------------------- |
| `def __init__`      | Mauvaise indentation            | Les affectations doivent être indentées à l’intérieur du constructeur.                 |
| `@setter`           | Décorateur invalide             | `@setter` seul n’existe pas. Il faut d’abord un `@property`, puis un `@<nom>.setter`.  |
| `def set_age(self)` | Mauvais nom et mauvaise logique | Ce n’est pas un setter correct, ni un vrai setter Python.                              |
| `input(int(...))`   | Appel incorrect à `input()`     | `int(...)` doit être appliqué **après** la saisie, pas **autour** de l’invite.         |
| `numero_diagnostic` | Attribut inexistant             | Mauvais nom : c’est `numero_dossier` et `diagnostic` qui sont définis dans `__init__`. |



### 2. Code corrigé

Voici la **version corrigée** avec une méthode `set_age` simple (sans utiliser `@property` ici pour simplifier) :

```python
from abc import ABC

class Patient(ABC):
    def __init__(self, nom: str, prenom: str, age: int, numero_dossier: str, diagnostic: str):
        self.nom = nom
        self.prenom = prenom
        self.age = age
        self.numero_dossier = numero_dossier
        self.diagnostic = diagnostic

    def set_age(self, new_age: int):
        if new_age < 0:
            print("Erreur! L'âge ne peut pas être négatif!")
        else:
            self.age = new_age

    def traiter(self):
        pass

    def __str__(self):
        return (f"Fiche Patient\n"
                f"Nom : {self.nom}\n"
                f"Prenom : {self.prenom}\n"
                f"Âge : {self.age}\n"
                f"Dossier : {self.numero_dossier}\n"
                f"Diagnostic : {self.diagnostic}")
```





# 4 -  Version corrigée avec `@property` et `@setter`

```python
from abc import ABC

class Patient(ABC):
    def __init__(self, nom: str, prenom: str, age: int, numero_dossier: str, diagnostic: str):
        self.nom = nom
        self.prenom = prenom
        self._age = age  # Utilisation d'un attribut "protégé" pour le setter
        self.numero_dossier = numero_dossier
        self.diagnostic = diagnostic

    @property
    def age(self) -> int:
        return self._age

    @age.setter
    def age(self, value: int):
        if value < 0:
            print("Erreur ! L'âge ne peut pas être négatif.")
        else:
            self._age = value

    def traiter(self):
        pass  # Méthode à implémenter dans les sous-classes si nécessaire

    def __str__(self) -> str:
        return (f"Fiche Patient\n"
                f"Nom        : {self.nom}\n"
                f"Prénom     : {self.prenom}\n"
                f"Âge        : {self.age}\n"
                f"Dossier    : {self.numero_dossier}\n"
                f"Diagnostic : {self.diagnostic}")
```



##  Exemple d’utilisation :

```python
p = Patient("Dupont", "Alice", 35, "D12345", "Grippe")
print(p)

p.age = -5  # Affiche : Erreur ! L'âge ne peut pas être négatif.
p.age = 42  # Met à jour l'âge
print(p.age)  # Affiche : 42
```



##  À retenir

| Élément              | Bonnes pratiques                                                                                            |
| -------------------- | ----------------------------------------------------------------------------------------------------------- |
| `@property`          | Permet d'accéder à un attribut comme s'il était public, tout en le contrôlant                               |
| `@<property>.setter` | Ajoute une logique de validation avant modification                                                         |
| `_attribut`          | Convention pour signaler un attribut « protégé » (non modifiable directement)                               |
| `ABC`                | Permet de définir une classe abstraite, utile si on veut forcer des sous-classes à implémenter des méthodes |




# 5 - Question Bonus – Analyse de comportement inattendu

Considérez la classe `Patient` corrigée avec la propriété `@age.setter`. On exécute le code suivant :

```python
p = Patient("Martin", "Paul", -10, "P999", "Rhume")  # âge négatif à l'initialisation
print(p.age)

p.age = -5  # tentative de modification
print(p.age)
```

#### Questions :

1. Le programme accepte-t-il la valeur négative `-10` lors de l’instanciation du patient ? Pourquoi ?
2. Que se passe-t-il lorsque l’on tente ensuite de modifier `p.age` à `-5` ? Quelle partie du code intervient ?
3. Expliquez **pourquoi** le contrôle de validité ne fonctionne **que** lors de la modification et non à la création.
4. Proposez une modification du code pour empêcher également l’attribution d’un âge négatif dans `__init__`.



### Éléments attendus dans la réponse 

1. **Oui**, la valeur `-10` est acceptée lors de l’instanciation car `__init__` assigne directement `self._age = age` sans passer par le setter.
2. Lors de l’appel `p.age = -5`, le **setter `@age.setter`** est activé, détecte la valeur négative, et affiche un message sans modifier l’attribut.
3. Le setter n’est **pas automatiquement appelé dans le constructeur**, car dans `__init__`, on assigne directement à `self._age`, donc **le contrôle est contourné**.
4. Pour renforcer la sécurité, on peut remplacer dans `__init__` :

```python
self._age = age
```

par :

- Ajout de la condition sur l'âge

