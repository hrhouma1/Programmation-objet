
# **EXAMEN – Programmation Python, UML, Git et Manipulation de Données**




# PARTIE 1 – Étude de cas UML (10 points)

> Voici un diagramme UML issu d’un logiciel de gestion de **pharmacie** :

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



# PARTIE 3 – Programmation orientée objet (10 points)

**Situation :**
Vous devez modéliser un système de réservation pour un cabinet médical.

1. La classe `Patient` contient un nom, un identifiant et une méthode `afficher_fiche()`.
2. La classe `RendezVous` contient la date, l’heure, et le médecin assigné.
3. Chaque patient peut avoir plusieurs rendez-vous.

**Question :**
Créez ces classes en Python, avec des méthodes permettant d’ajouter un rendez-vous à un patient et d’afficher tous ses rendez-vous.



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



# PARTIE 7 – Concepts fondamentaux (10 points)

*Répondez de manière claire et précise.*

1. Expliquez ce qu’est le **polymorphisme** avec un exemple.
2. Quelle est la différence entre une **composition** et une **agrégation** ?
3. Donnez un exemple d’usage de `lambda` en Python.
4. Quelle est l’utilité de la fonction `map()` ?
5. Expliquez brièvement l’intérêt de `super()` dans une classe héritée.

