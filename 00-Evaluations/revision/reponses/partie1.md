

# 1 - **Correction – Question 1 : Classe abstraite Patient**

```python
from abc import ABC, abstractmethod

class Patient(ABC):
    def __init__(self, nom: str, prenom: str, age: int, numero_dossier: str, diagnostic: str):
        self.nom = nom
        self.prenom = prenom
        self._age = age
        self.numero_dossier = numero_dossier
        self.diagnostic = diagnostic

    @property
    def age(self):
        return self._age

    @age.setter
    def age(self, value):
        if value < 0:
            raise ValueError("Erreur : l'âge ne peut pas être négatif.")
        self._age = value

    @abstractmethod
    def traiter(self):
        pass

    def __str__(self):
        return (
            f"Fiche Patient\n"
            f"Nom : {self.nom}\n"
            f"Prénom : {self.prenom}\n"
            f"Âge : {self.age} ans\n"
            f"Dossier : {self.numero_dossier}\n"
            f"Diagnostic : {self.diagnostic}"
        )

# Sous-classe minimale
class PatientTest(Patient):
    def traiter(self):
        pass

# Test
p = PatientTest("Dupont", "Marie", 45, "P1234", "Diabète de type 2")
print(p)
```

>  Cette question évalue : héritage, classe abstraite, décorateurs `@property`, `__str__`.



# 2 - **Correction – Question 2 : Urgence vs Suivi**

```python
class PatientUrgence(Patient):
    def __init__(self, nom, prenom, age, numero_dossier, diagnostic, gravite):
        super().__init__(nom, prenom, age, numero_dossier, diagnostic)
        self.gravite = gravite

    def traiter(self):
        print(f"Traitement en urgence (niveau {self.gravite}) pour {self.prenom} {self.nom}")

class PatientSuivi(Patient):
    def __init__(self, nom, prenom, age, numero_dossier, diagnostic, frequence_visites):
        super().__init__(nom, prenom, age, numero_dossier, diagnostic)
        self.frequence_visites = frequence_visites

    def traiter(self):
        print(f"Suivi programmé toutes les {self.frequence_visites} semaines pour {self.prenom} {self.nom}")

# Création des objets
urgence = PatientUrgence("Dupont", "Marie", 45, "P5678", "Douleurs thoraciques", 4)
suivi = PatientSuivi("Karim", "Ali", 62, "P8910", "Hypertension", 6)

# Appel des traitements
urgence.traiter()
suivi.traiter()
```

>  Cette question évalue : héritage, surcharge du constructeur, spécialisation de méthode, logique conditionnelle.



#  3 - **Correction – Question 3 : Comparaison et tri**

Ajout dans `Patient` :

```python
    def __eq__(self, other):
        if not isinstance(other, Patient):
            return NotImplemented
        return self.nom == other.nom and self.prenom == other.prenom

    def __lt__(self, other):
        return self.nom < other.nom
```

Ensuite, test du tri :

```python
p1 = PatientSuivi("Zola", "Émile", 50, "P0001", "Suivi régulier", 12)
p2 = PatientUrgence("Dupont", "Marie", 45, "P0002", "Urgence", 5)
p3 = PatientSuivi("Aubert", "Claire", 30, "P0003", "Suivi", 4)

patients = [p1, p2, p3]
patients_tries = sorted(patients)

for p in patients_tries:
    print(p)
```

>  Cette question évalue : redéfinition d'opérateurs (`__eq__`, `__lt__`), tri personnalisé, usage de `sorted`.


