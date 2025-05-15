
# **EXAMEN – Programmation Python, UML, Git et Manipulation de Données**




# PARTIE 1 – Étude de cas UML (10 points)

> Je vous présente un diagramme UML issu d’un logiciel de gestion de **pharmacie** :

```
+--------------------+        1        +---------------+
|    Pharmacie       |----------------|   Medicament  |
+--------------------+                +---------------+
| - nom : str        |                | - nom : str   |
| - adresse : str    |                | - code : str  |
|                    |                | - prix : float|
+--------------------+                +---------------+
| +ajouter(m : Medicament)           |
| +inventaire() : list[str]          |
+------------------------------------+
```

**Question :**
Rédigez le code Python correspondant à cette modélisation, avec les classes, constructeurs, méthodes, et types. Le programme ne doit pas contenir d'interaction utilisateur, uniquement les définitions.



#  CORRECTION – PARTIE 1 : UML → Code Python (10 points)



## **1. Analyse du diagramme UML**

Nous observons les éléments suivants :

* **Deux classes** :

  * `Pharmacie`
  * `Medicament`

* **Relation d'association** :

  * Une pharmacie possède plusieurs médicaments (multiplicité 1 → \*).

* **Attributs** :

  * `Pharmacie` : `nom` (str), `adresse` (str)
  * `Medicament` : `nom` (str), `code` (str), `prix` (float)

* **Méthodes** :

  * `Pharmacie` :

    * `ajouter(m : Medicament)` : ajoute un médicament
    * `inventaire() -> list[str]` : retourne une liste des noms de médicaments



## **2. Code Python correspondant**

```python
from typing import List

class Medicament:
    def __init__(self, nom: str, code: str, prix: float):
        self.nom = nom
        self.code = code
        self.prix = prix

class Pharmacie:
    def __init__(self, nom: str, adresse: str):
        self.nom = nom
        self.adresse = adresse
        self._medicaments: List[Medicament] = []

    def ajouter(self, m: Medicament) -> None:
        self._medicaments.append(m)

    def inventaire(self) -> List[str]:
        return [med.nom for med in self._medicaments]
```



## **3. Explication**

* La classe `Medicament` correspond strictement à la structure du diagramme.
* La classe `Pharmacie` contient une **liste privée** `_medicaments`, non visible dans le diagramme mais **déduite de la multiplicité**.
* La méthode `ajouter` ajoute un médicament à la liste.
* La méthode `inventaire` retourne une **liste de chaînes de caractères**, comme spécifié (`list[str]`), représentant les noms des médicaments présents.



<br/>
<br/>



# PARTIE 2 – Manipulation de fichiers et structures de données (10 points)

**Contexte :**
Une pharmacie stocke son inventaire dans un fichier `stock.json`. Voici un extrait :

```json
[
  {"nom": "Doliprane", "code": "A123", "prix": 4.5},
  {"nom": "Ibuprofène", "code": "B456", "prix": 5.9}
]
```

**Question :**
Écrivez un script Python qui lit ce fichier et affiche la liste des médicaments avec leur nom et prix, sous la forme :
`Doliprane - 4.5 $`

Utilisez la bibliothèque `json`.







# CORRECTION – PARTIE 2 : Manipulation de fichiers JSON (10 points)



## **1. Objectif de la question**

L'étudiant devait :

* Lire un fichier JSON contenant une liste de médicaments
* Parcourir cette liste
* Afficher le nom et le prix de chaque médicament sous la forme :
  `Doliprane - 4.5 $`

---

## **2. Script Python attendu**

```python
import json

# Lecture du fichier stock.json
with open("stock.json", "r", encoding="utf-8") as fichier:
    stock = json.load(fichier)

# Affichage des médicaments
for medicament in stock:
    nom = medicament["nom"]
    prix = medicament["prix"]
    print(f"{nom} - {prix} $")
```

---

## **3. Explication**

* `import json` : permet de charger des fichiers au format JSON (JavaScript Object Notation)
* `with open(...)` : ouverture sécurisée du fichier
* `json.load(fichier)` : transforme le contenu JSON en une liste de dictionnaires Python
* Le `for` permet de parcourir chaque dictionnaire représentant un médicament
* L'utilisation de `f-strings` permet d’afficher la ligne dans le format demandé
















<br/>
<br/>



# PARTIE 3 – Programmation orientée objet (10 points)

**Situation :**
Vous devez modéliser un système de réservation pour un cabinet médical.

1. La classe `Patient` contient un nom, un identifiant et une méthode `afficher_fiche()`.
2. La classe `RendezVous` contient la date, l’heure, et le médecin assigné.
3. Chaque patient peut avoir plusieurs rendez-vous.

**Question :**
Créez ces classes en Python, avec des méthodes permettant d’ajouter un rendez-vous à un patient et d’afficher tous ses rendez-vous.





# CORRECTION – PARTIE 3 : Programmation orientée objet (10 points)



## **1. Objectif de la question**

L’étudiant devait :

* Créer deux classes principales : `Patient` et `RendezVous`
* Intégrer une relation 1→\* entre `Patient` et `RendezVous`
* Ajouter une méthode pour afficher les rendez-vous d’un patient
* Utiliser des types et constructeurs corrects

---

## **2. Code Python attendu**

```python
from typing import List

class RendezVous:
    def __init__(self, date: str, heure: str, medecin: str):
        self.date = date
        self.heure = heure
        self.medecin = medecin

    def afficher(self) -> str:
        return f"{self.date} à {self.heure} avec Dr. {self.medecin}"

class Patient:
    def __init__(self, nom: str, identifiant: str):
        self.nom = nom
        self.identifiant = identifiant
        self._rendez_vous: List[RendezVous] = []

    def ajouter_rdv(self, rdv: RendezVous) -> None:
        self._rendez_vous.append(rdv)

    def afficher_fiche(self) -> None:
        print(f"Patient : {self.nom} (ID : {self.identifiant})")
        if not self._rendez_vous:
            print("Aucun rendez-vous.")
        else:
            for rdv in self._rendez_vous:
                print(rdv.afficher())
```



## **3. Explication pédagogique**

* La classe `RendezVous` stocke les informations essentielles : date, heure, médecin.
* La méthode `afficher()` de `RendezVous` retourne une chaîne proprement formatée.
* La classe `Patient` contient une liste de rendez-vous (relation 1 → \* déduite).
* La méthode `ajouter_rdv()` permet d’ajouter un objet `RendezVous` à un patient.
* La méthode `afficher_fiche()` affiche l’identité du patient suivie de tous ses rendez-vous.








<br/>
<br/>


# PARTIE 4 – Git et collaboration (10 points)

**Scénario :**
Un projet d’équipe est en cours. Voici l’historique :

* Vous êtes sur la branche `analyse-donnees`
* Vous devez intégrer vos changements à `main`
* Une autre personne a aussi modifié `main`

**Question :**

1. Quelle commande allez-vous utiliser pour intégrer vos modifications sans écraser celles des autres ?
2. Décrivez étape par étape ce que fait la commande `git fetch` et en quoi elle diffère de `git pull`.
3. Une fois la fusion faite, quelle commande permet de visualiser l’historique des branches de façon graphique ?





# CORRECTION – PARTIE 4 : Git et collaboration (10 points)


## **1. Objectif de la question**

L’étudiant devait démontrer sa compréhension de :

* L’intégration de branches (fusion, rebase)
* La différence entre `git fetch` et `git pull`
* L’utilisation d’outils d’analyse d’historique Git graphique

---

## **2. Correction attendue**

### **Question 1 : Quelle commande allez-vous utiliser pour intégrer vos modifications sans écraser celles des autres ?**

* **Réponse attendue :**

```bash
git merge main
```

**Explication :**
Depuis la branche `analyse-donnees`, on fusionne les changements de `main` **sans écraser** quoi que ce soit. `git merge` crée un commit de fusion si nécessaire.

**Alternative acceptable (avancé) :**

```bash
git rebase main
```

Mais **seulement** si aucun autre collaborateur ne travaille sur `analyse-donnees`.

---

### **Question 2 : Décrivez étape par étape ce que fait la commande `git fetch` et en quoi elle diffère de `git pull`.**

* **Réponse attendue :**

| Commande    | Fonction                                                                                                                                                                                    |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `git fetch` | Récupère les dernières mises à jour du serveur **sans modifier** le code local. Il met à jour les pointeurs distants (ex : `origin/main`), mais n’intègre rien dans votre branche actuelle. |
| `git pull`  | Fait un `fetch` **suivi automatiquement d’un `merge`** ou d’un `rebase`. Cela met à jour votre code local **et intègre immédiatement** les changements.                                     |

**Résumé pédagogique :**

* `git fetch` = **mettre à jour silencieusement**
* `git pull` = **mettre à jour ET fusionner**

---

### **Question 3 : Une fois la fusion faite, quelle commande permet de visualiser l’historique des branches de façon graphique ?**

* **Réponse attendue :**

```bash
git log --graph --oneline --all
```

**Explication :**
Cette commande affiche l’historique de toutes les branches sous forme d’un **graph arborescent**, avec chaque commit résumé sur une seule ligne.

**Autres alternatives acceptables (bonus) :**

* `gitk` (si installé)
* Interfaces comme GitKraken ou l’onglet "Source Control" de VS Code


<br/>
<br/>


# PARTIE 5 – Lecture de code et compréhension fonctionnelle (10 points)

```python
class Client:
    def __init__(self, nom, panier):
        self.nom = nom
        self.panier = panier

    def total(self):
        return sum(self.panier)

c1 = Client("Alice", [10.5, 22.3, 5.0])
print(c1.total())
```

**Questions :**

1. Que va afficher ce programme ?
2. Expliquez pas à pas le rôle de chaque ligne.
3. Pourquoi utilise-t-on `sum()` ici, et que serait une alternative ?






# CORRECTION – PARTIE 5 : Lecture de code et compréhension fonctionnelle (10 points)


## **1. Code proposé à l’étudiant**

```python
class Client:
    def __init__(self, nom, panier):
        self.nom = nom
        self.panier = panier

    def total(self):
        return sum(self.panier)

c1 = Client("Alice", [10.5, 22.3, 5.0])
print(c1.total())
```

---

## **2. Questions et corrections**

---

### **Question 1 : Que va afficher ce programme ?**

* **Réponse attendue :**

```
37.8
```

**Explication :**
La méthode `total()` additionne les valeurs `[10.5, 22.3, 5.0]` via la fonction `sum()`, ce qui donne 37.8.

---

### **Question 2 : Expliquez pas à pas le rôle de chaque ligne.**

* **Correction attendue :**

1. **Classe `Client`** : définit un client avec un nom et un panier (liste de prix).
2. `__init__()` : initialise les attributs `nom` et `panier`.
3. `total()` : calcule le total du panier à l’aide de `sum`.
4. `c1 = Client(...)` : crée un objet `Client` nommé `"Alice"` avec 3 articles.
5. `print(c1.total())` : appelle la méthode `total()` et affiche 37.8.

---

### **Question 3 : Pourquoi utilise-t-on `sum()` ici, et que serait une alternative ?**

* **Réponse attendue :**

- La fonction `sum()` est utilisée pour **additionner tous les éléments d'une liste** de manière concise et efficace.
- **Alternative possible :**

```python
def total(self):
    total = 0
    for prix in self.panier:
        total += prix
    return total
```

Cette méthode manuelle fait la même chose mais est plus longue et moins lisible.








<br/>
<br/>




# PARTIE 6 – Format de données et traitement (10 points)

**Contexte :**
Une entreprise reçoit des données clients sous forme de fichiers `.csv`. Voici un extrait :

```
nom,email,age
Marc,marc@example.com,32
Julie,julie@example.com,27
```

**Question :**

1. Quelle bibliothèque Python est la plus adaptée pour lire ce fichier et effectuer des statistiques ?
2. Écrivez un code Python affichant la moyenne d’âge.
3. Pourquoi utiliser `csv` plutôt que `txt` pour ces données ?



# CORRECTION – PARTIE 6 : Format de données et traitement (10 points)



## **1. Objectif de la question**

L’étudiant devait :

* Identifier la bibliothèque Python appropriée pour lire un fichier `.csv`
* Calculer une statistique à partir des données (moyenne d’âge)
* Justifier pourquoi un format CSV est préférable à un fichier texte brut

---

## **2. Réponses attendues**

---

### **Question 1 : Quelle bibliothèque Python est la plus adaptée pour lire ce fichier et effectuer des statistiques ?**

* **Réponse correcte :**

```python
import csv
```

ou (encore mieux pour les statistiques) :

```python
import pandas as pd
```

**Explication :**

* `csv` est une bibliothèque standard, légère et efficace pour lire les fichiers CSV ligne par ligne.
* `pandas` est une bibliothèque plus puissante pour manipuler des tableaux de données et effectuer des statistiques comme `mean()`.

---

### **Question 2 : Écrivez un code Python affichant la moyenne d’âge.**

#### **Option 1 : avec la bibliothèque `csv`**

```python
import csv

ages = []

with open("clients.csv", newline='', encoding="utf-8") as fichier:
    lecteur = csv.DictReader(fichier)
    for ligne in lecteur:
        ages.append(int(ligne["age"]))

moyenne = sum(ages) / len(ages)
print(f"Moyenne d’âge : {moyenne}")
```

#### **Option 2 : avec la bibliothèque `pandas` (recommandée)**

```python
import pandas as pd

df = pd.read_csv("clients.csv")
moyenne = df["age"].mean()
print(f"Moyenne d’âge : {moyenne}")
```

---

### **Question 3 : Pourquoi utiliser `csv` plutôt que `txt` pour ces données ?**

* **Réponse attendue :**

- Le format `.csv` permet de **structurer les données en colonnes**, ce qui facilite leur traitement automatique.
- Contrairement au `.txt`, les fichiers CSV permettent :

  * Un **parsing automatisé**
  * Une **interprétation cohérente** des champs (ex : `nom`, `email`, `age`)
  * Une compatibilité avec des outils de traitement comme Excel, pandas, SQL, etc.

**Résumé :**

> Le CSV est un format **structuré**, lisible par l’humain **et** par la machine. Le `.txt` est un format libre mais non structuré, donc moins fiable pour le traitement automatique de données tabulaires.


<br/>
<br/>


# PARTIE 7 – Concepts fondamentaux (10 points)

*Répondez de manière claire et précise.*

1. Expliquez ce qu’est le **polymorphisme** avec un exemple.
2. Quelle est la différence entre une **composition** et une **agrégation** ?
3. Donnez un exemple d’usage de `lambda` en Python.
4. Quelle est l’utilité de la fonction `map()` ?
5. Expliquez brièvement l’intérêt de `super()` dans une classe héritée.





# CORRECTION – PARTIE 7 : Concepts fondamentaux (10 points)



## **1. Objectif de la question**

L’étudiant devait démontrer sa compréhension de plusieurs concepts clés de la programmation Python et de la programmation orientée objet.

---

## **2. Réponses attendues**

---

### **Question 1 : Expliquez ce qu’est le polymorphisme avec un exemple.**

* **Réponse attendue :**

> Le **polymorphisme** permet d’utiliser la **même méthode** sur différents types d’objets, chacun ayant sa propre implémentation.

**Exemple :**

```python
class Chat:
    def parler(self):
        print("Miaou")

class Chien:
    def parler(self):
        print("Aboie")

def faire_parler(animal):
    animal.parler()

faire_parler(Chat())   # Miaou
faire_parler(Chien())  # Aboie
```

---

### **Question 2 : Quelle est la différence entre une composition et une agrégation ?**

* **Réponse attendue :**

| Terme           | Définition                                                                                                                                 |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Composition** | Relation forte : la sous-classe **n’existe pas sans** la classe principale. Si la classe principale est supprimée, l’autre aussi.          |
| **Agrégation**  | Relation faible : les deux classes peuvent **vivre indépendamment**. La suppression de l’une **n’entraîne pas** la suppression de l’autre. |

**Exemples :**

* Composition : une **voiture** contient un **moteur** → le moteur dépend de la voiture.
* Agrégation : une **université** a des **étudiants**, mais un étudiant existe en dehors de l’université.

---

### **Question 3 : Donnez un exemple d’usage de `lambda` en Python.**

* **Réponse attendue :**

```python
carres = list(map(lambda x: x**2, [1, 2, 3, 4]))
print(carres)  # [1, 4, 9, 16]
```

**Explication :**
La fonction `lambda` permet de définir une **fonction anonyme**, souvent utilisée avec `map()`, `filter()`, `sorted()`.

---

### **Question 4 : Quelle est l’utilité de la fonction `map()` ?**

* **Réponse attendue :**

> `map()` applique une **fonction** à **chaque élément** d’un itérable (ex : liste) et retourne un nouvel itérable (souvent converti en liste).

**Exemple :**

```python
noms = ["alice", "bob"]
majuscules = list(map(str.upper, noms))  # ['ALICE', 'BOB']
```

---

### **Question 5 : Expliquez brièvement l’intérêt de `super()` dans une classe héritée.**

* **Réponse attendue :**

> `super()` permet d’**appeler une méthode** (souvent le constructeur) de la **classe parente**, afin de ne pas réécrire le code hérité.

**Exemple :**

```python
class Animal:
    def __init__(self, nom):
        self.nom = nom

class Chien(Animal):
    def __init__(self, nom, race):
        super().__init__(nom)
        self.race = race
```

