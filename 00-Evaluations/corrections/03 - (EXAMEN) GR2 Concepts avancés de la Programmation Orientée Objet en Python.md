# **Examen 1 : Concepts avancés de la Programmation Orientée Objet en Python (Médecin)**  

**Objectif :** Cet examen vous guidera **progressivement** à travers la création d'une classe et son enrichissement avec des **attributs, méthodes, héritage, utilisation de `super()`, héritage multiple, et vérifications de types** en Python.  

**Règle :** Vous devez **réécrire le code complet** pour chaque question en suivant les instructions et les pseudo-codes fournis.  

---

## **Partie 1 : Création d'une classe vide**  

### **Question 1 : Définition d'une classe `Medecin`**  
Définissez une classe `Medecin` en Python, sans rien ajouter à l'intérieur.  

```plaintext
Définir une classe Medecin  
Ajouter une instruction minimale pour éviter une erreur  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```
+-----------------+
|    Medecin     |
+-----------------+
|                |
+-----------------+
```

---

## **Partie 2 : Ajout des attributs d'instance**  

### **Question 2 : Définition des attributs `nom` et `specialite`**  
Ajoutez les **attributs d’instance** `nom` et `specialite` à la classe `Medecin`, **sans constructeur**.  

```plaintext
Déclarer les attributs d’instance nom et specialite sans constructeur  
Créer un objet m1 de Medecin  
Assigner un nom et une spécialité  
Afficher ces valeurs  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
+-----------------+
```

---

## **Partie 3 : Ajout d'un constructeur (`__init__`)**  

### **Question 3 : Ajout du constructeur `__init__`**  
Ajoutez un **constructeur (`__init__`)** qui prend en paramètres `nom` et `specialite`, et stocke ces valeurs dans les attributs correspondants.  

```plaintext
Définir une méthode __init__(self, nom, specialite)  
Initialiser les attributs d'instance nom et specialite  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
+-----------------+
| + __init__()   |
+-----------------+
```

---

## **Partie 4 : Ajout d'une méthode d'instance**  

### **Question 4 : Ajout de la méthode `prescrire_traitement()`**  
Ajoutez une **méthode `prescrire_traitement()`** qui retourne une phrase indiquant que le médecin prescrit un traitement.  

```plaintext
Définir une méthode prescrire_traitement(self)  
Retourner une chaîne contenant nom et specialite  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
+-----------------+
| + __init__()   |
| + prescrire_traitement() |
+-----------------+
```

---

## **Partie 5 : Ajout d’un attribut de classe**  

### **Question 5 : Ajout de l’attribut `hopital`**  
Ajoutez un **attribut de classe** `hopital` (qui vaut `"Hôpital Général"` pour tous les médecins).  

```plaintext
Déclarer un attribut de classe hopital avec la valeur "Hôpital Général"  
Modifier `prescrire_traitement()` pour inclure l’hôpital  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
Le Dr. Dupont, spécialiste en cardiologie, prescrit un traitement à l'Hôpital Général.
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  <-- Attribut de classe
+-----------------+
| + __init__()   |
| + prescrire_traitement() |
+-----------------+
```




---

## **Partie 6 : Ajout d'une méthode de classe**  

### **Question 6 : Ajout de `changer_hopital()`**  
Ajoutez une **méthode de classe `changer_hopital(nouveau_hopital)`** pour modifier `hopital`.

```plaintext
Définir une méthode de classe changer_hopital(cls, nouveau_hopital)  
Modifier l'attribut de classe hopital avec la nouvelle valeur  
Afficher un médecin avant et après le changement  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
Avant modification : Le Dr. Dupont, spécialiste en cardiologie, travaille à l'Hôpital Général.
Après modification : Le Dr. Dupont, spécialiste en cardiologie, travaille au Centre Hospitalier Universitaire.
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  
+-----------------+
| + __init__()   |
| + prescrire_traitement() |
| + changer_hopital() |  <-- Méthode de classe
+-----------------+
```

---

## **Partie 7 : Ajout d’un attribut privé**  

### **Question 7 : Ajout de `__experience` et affichage**  

Ajoutez un **attribut privé `__experience`** dans `__init__()`, puis créez une **méthode `afficher_experience()`**.

```plaintext
Dans __init__(), ajouter un attribut privé __experience  
Définir une méthode afficher_experience()  
Retourner une phrase contenant la valeur de __experience  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
Le Dr. Dupont a 15 ans d'expérience en cardiologie.
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  
| - __experience |  <-- Attribut privé
+-----------------+
| + __init__()   |
| + prescrire_traitement() |
| + changer_hopital() |
| + afficher_experience() |
+-----------------+
```

---

## **Partie 8 : Utilisation de `lambda` et des fonctions d'ordre supérieur**  

### **Question 8 : Ajout de `estimer_salaire(lambda_function)`**  

Ajoutez une **méthode `estimer_salaire(lambda_function)`** qui utilise une **fonction lambda** pour estimer le salaire en fonction de l'expérience.

```plaintext
Définir une méthode estimer_salaire(self, lambda_function)  
Appliquer la fonction lambda sur __experience et retourner le salaire estimé  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
Le Dr. Dupont a un salaire estimé à 9000 $ par mois.
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  
| - __experience |  
+-----------------+
| + __init__()   |
| + prescrire_traitement() |
| + changer_hopital() |
| + afficher_experience() |
| + estimer_salaire(lambda_function) |  <-- Utilisation de lambda
+-----------------+
```

---

## **Partie 9 : Utilisation des compréhensions de liste avec `lambda`**  

### **Question 9 : Ajout de `estimer_salaires_annees()`**  

Ajoutez une **méthode `estimer_salaires_annees(salaire_base, annees)`** qui retourne une **liste des salaires estimés** sur plusieurs années.

```plaintext
Définir une méthode estimer_salaires_annees(self, salaire_base, annees)  
Retourner une liste des salaires estimés sur plusieurs années  
Utiliser une compréhension de liste et une fonction lambda  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
Salaires estimés sur 5 ans : [9000, 9500, 10000, 10500, 11000] €
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  
| - __experience |  
+-----------------+
| + __init__()   |
| + prescrire_traitement() |
| + changer_hopital() |
| + afficher_experience() |
| + estimer_salaire(lambda_function) |
| + estimer_salaires_annees(salaire_base, annees) | <-- Compréhension de liste
+-----------------+
```

---

## **Partie 10 : Implémentation de `__str__`**  

### **Question 10 : Modifier `__str__` pour afficher une représentation détaillée**  
Ajoutez une méthode `__str__()` pour retourner une **chaîne formatée** des informations du médecin.

```plaintext
Définir une méthode __str__(self)  
Retourner une chaîne formatée contenant nom, spécialité, expérience et hôpital  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
Le Dr. Dupont, spécialiste en cardiologie, a 15 ans d'expérience et travaille à l'Hôpital Général.
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  
| - __experience |  
+-----------------+
| + __init__()   |
| + prescrire_traitement() |
| + changer_hopital() |
| + afficher_experience() |
| + estimer_salaire(lambda_function) |
| + estimer_salaires_annees(salaire_base, annees) |
| + __str__() |  <-- Méthode spéciale
+-----------------+
```



---

## **Partie 11 : Implémentation de `__str__` avec affichage ASCII**  

### **Question 11 : Modifier `__str__` pour afficher une représentation ASCII détaillée**  
Modifiez `__str__()` pour **afficher un tableau ASCII bien formaté**.

```plaintext
Modifier __str__() pour afficher un tableau ASCII  
Inclure nom, spécialité, expérience et hôpital  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
---------------------------------
|         Informations         |
---------------------------------
| Nom        : Dr. Dupont       |
| Spécialité : Cardiologie      |
| Expérience : 15 ans           |
| Hôpital    : Hôpital Général  |
---------------------------------
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  
| - __experience |  
+-----------------+
| + __init__()   |
| + prescrire_traitement() |
| + changer_hopital() |
| + afficher_experience() |
| + estimer_salaire(lambda_function) |
| + estimer_salaires_annees(salaire_base, annees) |
| + __str__()  |  <-- Affichage ASCII
+-----------------+
```

---

## **Partie 12 : Héritage simple**  

### **Question 12 : Création de `Chirurgien`**  
Ajoutez une **classe `Chirurgien` qui hérite de `Medecin`** et ajoute un attribut `specialisation_chirurgicale`.

```plaintext
Créer une classe Chirurgien qui hérite de Medecin  
Ajouter un attribut specialisation_chirurgicale  
Ajouter une méthode effectuer_operation()  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```
+-----------------+
|   Chirurgien   |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  
| - __experience |  
| - specialisation_chirurgicale |  <-- Nouvel attribut
+-----------------+
| + __init__()   |
| + effectuer_operation()  |
+-----------------+
```

---

## **Partie 13 : Utilisation de `super()` dans `Chirurgien`**  

### **Question 13 : Modifier `Chirurgien` pour utiliser `super()`**  
Modifiez la classe **`Chirurgien`** pour appeler **le constructeur de `Medecin` avec `super()`** et ajouter les informations de spécialisation chirurgicale dans **`__str__()`**.

```plaintext
Modifier __init__() pour appeler le constructeur parent avec super()  
Modifier __str__() pour appeler la méthode parent avec super().__str__()  
Ajouter les informations sur la spécialisation chirurgicale à la sortie  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
---------------------------------
|         Informations         |
---------------------------------
| Nom        : Dr. Martin       |
| Spécialité : Chirurgie        |
| Expérience : 20 ans           |
| Hôpital    : Hôpital Saint-Luc|
| Spécialité Chirurgicale : Neurochirurgie |
---------------------------------
```

```
+-----------------+
|   Chirurgien   |
+-----------------+
| - nom          |
| - specialite   |
| - hopital      |  
| - __experience |  
| - specialisation_chirurgicale |  
+-----------------+
| + __init__()   |  <-- Utilisation de super()
| + effectuer_operation() |
| + __str__()  |  <-- Utilisation de super()
+-----------------+
```

---

## **Partie 14 : Héritage multiple avec `Chercheur`**  

### **Question 14 : Ajout de `Chercheur` et `MedecinChercheur`**  

```plaintext
Créer une classe Chercheur avec un attribut domaine_recherche  
Créer MedecinChercheur qui hérite de Medecin et Chercheur  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```
+------------------+
|    Chercheur    |
+------------------+
| - domaine_recherche |
+------------------+
| + __init__()    |
| + publier_article() |
+------------------+

+------------------------------+
|  MedecinChercheur           |
+------------------------------+
| - nom                        |
| - specialite                 |
| - hopital                    |
| - __experience               |
| - domaine_recherche          |
+------------------------------+
| + __init__()                 |
| + publier_article()          |
| + __str__()                  |
+------------------------------+
```

---

## **Partie 15 : Vérification des types avec `type()`, `isinstance()` et `issubclass()`**  

```plaintext
Définir une méthode de classe verifier_type(cls, objet)  
Utiliser type() pour afficher le type exact de l’objet  
Utiliser isinstance(objet, Medecin) pour vérifier si l’objet est une instance  
Utiliser issubclass(Chirurgien, Medecin) pour vérifier l’héritage  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
+-----------------+
| + __init__()   |
| + verifier_type(objet)  |
+-----------------+
```

---

## **Partie 16 : Récapitulatif – Getters, Setters et Héritage**  

### **Question 16 : Création et modification de plusieurs types de médecins**  

Créez plusieurs types de médecins (`Medecin`, `Chirurgien`, `MedecinChercheur`) avec des valeurs différentes.  
Utilisez des **getters et setters** pour accéder et modifier l’attribut privé `__experience`.  
Enfin, affichez les informations de tous les médecins créés.  

```plaintext
Définir des getters et setters pour l'attribut __experience  
Créer 5 médecins de différents types  
Modifier l'expérience de certains médecins avec le setter  
Afficher les informations de chaque médecin  
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

📌 **💡 Output attendu :**  
```
---------------------------------
|         Informations         |
---------------------------------
| Nom        : Dr. Dupont       |
| Spécialité : Cardiologie      |
| Expérience : 15 ans           |
| Hôpital    : Hôpital Général  |
---------------------------------

---------------------------------
|         Informations         |
---------------------------------
| Nom        : Dr. Martin       |
| Spécialité : Chirurgie        |
| Expérience : 20 ans           |
| Hôpital    : Hôpital Saint-Luc|
| Spécialité Chirurgicale : Neurochirurgie |
---------------------------------

---------------------------------
|         Informations         |
---------------------------------
| Nom        : Dr. Lefebvre     |
| Spécialité : Pédiatrie        |
| Expérience : 10 ans           |
| Hôpital    : Clinique Sud     |
---------------------------------

---------------------------------
|         Informations         |
---------------------------------
| Nom        : Dr. Laurent      |
| Spécialité : Recherche        |
| Expérience : 12 ans           |
| Hôpital    : Institut Pasteur |
| Domaine de Recherche : Immunologie |
---------------------------------

---------------------------------
|         Informations         |
---------------------------------
| Nom        : Dr. Simon        |
| Spécialité : Médecine interne |
| Expérience : 18 ans           |
| Hôpital    : CHU Lyon         |
---------------------------------
```

```
+-----------------+
|    Medecin     |
+-----------------+
| - nom          |
| - specialite   |
| - __experience |
+-----------------+
| + __init__()   |
| + decrire()    |
| + get_experience() |
| + set_experience() |
+-----------------+
```

