# **Examen : Programmation Orientée Objet en Python avec Décorateurs**  

## **Règles :**  
- **Réécrivez le code complet** pour chaque question.  
- **Chaque question s’appuie sur la précédente** et enrichit la classe progressivement.  
- **Aucune exception** ne doit être levée. Utilisez **if, else et while** pour la validation.  
- **Les décorateurs doivent être utilisés autant que possible**.  

## Introduction:

- Cet examen couvre les bases de la **POO en Python**, tout en introduisant **beaucoup de décorateurs**, sans exceptions, et avec des **structures conditionnelles** (`if, else, while`).


## **Partie 1 : Création et initialisation d'une classe**

### **Question 1 : Classe `Vehicule` avec un constructeur**  
**Énoncé :**  
Définissez une classe `Vehicule` qui contient un constructeur `__init__()` avec trois attributs :  
- `marque` (chaîne de caractères)  
- `modele` (chaîne de caractères)  
- `kilometrage` (nombre entier)  

```python
...........................................................
...........................................................
```

---

### **Question 2 : Getters et Setters avec `@property` et validation simple**  
**Énoncé :**  
- Ajoutez **des getters et setters** pour `kilometrage` en utilisant `@property` et `@kilometrage.setter`.  
- Assurez-vous que **kilometrage ne soit pas négatif** en utilisant `if`.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", -100)
print(v.kilometrage)  # Doit afficher 0 car un kilométrage négatif n'est pas autorisé
```

---

### **Question 3 : Méthode `afficher_infos()` et décorateur `@property` pour `description`**  
**Énoncé :**  
- Ajoutez une méthode `afficher_infos()` qui affiche les informations du véhicule.  
- Ajoutez un **décorateur `@property`** `description` qui retourne une chaîne de caractères sous la forme :  
  `"Marque: Toyota | Modèle: Corolla | Kilométrage: 100000 km"`  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Corolla", 100000)
print(v.description)  
# Doit afficher : "Marque: Toyota | Modèle: Corolla | Kilométrage: 100000 km"
```

---

## **Partie 2 : Méthodes de classe et statiques**

### **Question 4 : Attribut de classe `nombre_vehicules` et méthode de classe `total_vehicules()`**  
**Énoncé :**  
- Ajoutez un **attribut de classe** `nombre_vehicules` initialisé à 0.  
- Dans `__init__()`, **augmentez** `nombre_vehicules` à chaque création d’un véhicule.  
- Ajoutez une **méthode de classe** `total_vehicules()` qui retourne le nombre total de véhicules créés.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v1 = Vehicule("Renault", "Clio", 50000)
v2 = Vehicule("Peugeot", "208", 30000)
print(Vehicule.total_vehicules())  # Doit afficher 2
```

---

### **Question 5 : Méthode statique `est_kilometrage_faible(km)`**  
**Énoncé :**  
Ajoutez une **méthode statique** `est_kilometrage_faible(km)` qui retourne :  
- `True` si le kilométrage est inférieur à **50 000 km**  
- `False` sinon  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
print(Vehicule.est_kilometrage_faible(40000))  # True
print(Vehicule.est_kilometrage_faible(80000))  # False
```

---

## **Partie 3 : Héritage et surcharge de méthodes**

### **Question 6 : Classe `Voiture` qui hérite de `Vehicule` avec un décorateur `@property`**  
**Énoncé :**  
- Créez une classe `Voiture` qui hérite de `Vehicule`.  
- Ajoutez un **attribut `nombre_portes`** (4 par défaut).  
- Ajoutez un **décorateur `@property`** `details` qui affiche :  
  `"Toyota Corolla | 4 portes | 100000 km"`  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Voiture("Toyota", "Corolla", 100000)
print(v.details)  
# Doit afficher : "Toyota Corolla | 4 portes | 100000 km"
```

---

### **Question 7 : Classe `Camion` qui hérite de `Vehicule` avec une surcharge de `afficher_infos()`**  
**Énoncé :**  
- Créez une classe `Camion` qui hérite de `Vehicule`.  
- Ajoutez un attribut `charge_max` (en tonnes, par défaut 5).  
- Redéfinissez `afficher_infos()` pour inclure la charge maximale.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
c = Camion("Volvo", "FH16", 200000)
c.afficher_infos()
# Doit afficher : "Marque: Volvo | Modèle: FH16 | Kilométrage: 200000 km | Charge max: 5 tonnes"
```

---

## **Partie 4 : Décorateurs avancés**

### **Question 8 : Ajout d’un décorateur `@verifier_kilometrage`**  
**Énoncé :**  
- Ajoutez un **décorateur** `@verifier_kilometrage` pour s'assurer que `kilometrage` ne dépasse pas `500000`.  
- Si `kilometrage` est trop grand, réduisez-le à `500000` avec un message d'avertissement.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Fiat", "Punto", 600000)
print(v.kilometrage)  # Doit afficher 500000 avec un message d’avertissement
```

---

### **Question 9 : Décorateur `@compter_appels` pour une méthode de calcul**  
**Énoncé :**  
- Ajoutez une **méthode `calculer_age(annee_achat)`** qui retourne l’âge du véhicule.  
- Utilisez un **décorateur `@compter_appels`** qui compte et affiche combien de fois la méthode a été appelée.  

```python
...........................................................
...........................................................
```

#### **Test attendu :**  
```python
v = Vehicule("Toyota", "Yaris", 150000)
print(v.calculer_age(2015))  # Doit afficher l'âge du véhicule
print(v.calculer_age(2010))  # Doit afficher l'âge du véhicule et le nombre d’appels
```

---

## **Partie 5 : Récapitulatif et création d'instances**

### **Question 10 : Création de plusieurs véhicules et affichage des détails**  
**Énoncé :**  
- Instanciez **5 véhicules différents** avec des valeurs variées.  
- Affichez leurs **informations complètes** à l’aide des méthodes définies précédemment.  

```python
...........................................................
...........................................................
```



