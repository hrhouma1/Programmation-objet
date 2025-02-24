## 📌 **Héritage en Python : Exemple pédagogique**

L'héritage permet de créer une **classe parent** et de faire hériter des **classes enfants** qui reprennent ses caractéristiques et peuvent les enrichir.

### **Diagramme ASCII de l'héritage**
Voici une représentation ASCII de la hiérarchie que nous allons coder :

```
          ┌──────────────┐
          │   Animal     │
          ├──────────────┤
          │ + nom        │
          │ + age        │
          │ + se_deplacer() │
          └──────┬───────┘
                 │
        ┌──────────────┐
        │  Personne    │  <-- Hérite de Animal
        ├──────────────┤
        │ + profession │
        │ + parler()   │
        └──────┬───────┘
               │
   ┌──────────────────┬──────────────────┐
   │ Professeur       │ Étudiant          │  <-- Héritent de Personne
   ├──────────────────┤──────────────────┤
   │ + matiere        │ + niveau          │
   │ + enseigner()    │ + etudier()       │
   └──────────────────┴──────────────────┘
```

---

### **📌 Implémentation en Python**

Nous allons implémenter cette hiérarchie avec des **classes** en Python.

#### **1️⃣ Classe de base : `Animal`**
```python
class Animal:
    def __init__(self, nom, age):
        self.nom = nom
        self.age = age

    def se_deplacer(self):
        return f"{self.nom} se déplace."
```

---

#### **2️⃣ Classe intermédiaire : `Personne` (hérite de `Animal`)**
```python
class Personne(Animal):
    def __init__(self, nom, age, profession):
        super().__init__(nom, age)
        self.profession = profession

    def parler(self):
        return f"{self.nom} dit : Bonjour !"
```

---

#### **3️⃣ Classes finales : `Professeur` et `Étudiant` (héritent de `Personne`)**

```python
class Professeur(Personne):
    def __init__(self, nom, age, matiere):
        super().__init__(nom, age, "Professeur")
        self.matiere = matiere

    def enseigner(self):
        return f"Le professeur {self.nom} enseigne {self.matiere}."
```

```python
class Etudiant(Personne):
    def __init__(self, nom, age, niveau):
        super().__init__(nom, age, "Étudiant")
        self.niveau = niveau

    def etudier(self):
        return f"L'étudiant {self.nom} étudie au niveau {self.niveau}."
```

---

### **📌 Test de notre hiérarchie**
On va créer un **professeur** et un **étudiant** pour voir comment ils se comportent.

```python
# Création des objets
prof = Professeur("Dr. Dupont", 45, "Mathématiques")
etudiant = Etudiant("Alice", 20, "Licence 2")

# Affichage des informations et appel des méthodes
print(prof.parler())  # Dr. Dupont dit : Bonjour !
print(prof.enseigner())  # Le professeur Dr. Dupont enseigne Mathématiques.

print(etudiant.parler())  # Alice dit : Bonjour !
print(etudiant.etudier())  # L'étudiant Alice étudie au niveau Licence 2.
```

---

### **📌 Explication ultra simplifiée**
1. **`Animal`** est la classe de base avec `nom`, `age` et `se_deplacer()`.
2. **`Personne`** hérite d’`Animal`, ajoute `profession` et `parler()`.
3. **`Professeur`** et **`Étudiant`** héritent de `Personne`, chacun avec ses propres attributs (`matiere`, `niveau`) et méthodes (`enseigner()`, `etudier()`).

---

### **📌 Résumé**
✅ Héritage **progressif** (de `Animal` → `Personne` → `Professeur`/`Étudiant`).  
✅ **Réutilisation** du code de `Animal` et `Personne`.  
✅ **Extensibilité** : on peut ajouter d’autres sous-classes facilement.

