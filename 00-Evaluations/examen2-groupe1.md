# **Examen 2 – Programmation Orientée Objet en Python**  
**Date :** Lundi 31 avril  
**Durée :** 1h30  
**Documentation :** Interdite (sauf une feuille manuscrite recto verso)  
**Barème total : 100 points**



# **Partie 1 – Classes de base (10 points)**

### **Question 1 (10 points)**  
Créer une classe nommée `Livre` avec les caractéristiques suivantes :  
- Attributs : `titre` (str), `auteur` (str), `pages` (int)  
- Un constructeur permettant d’initialiser ces trois attributs  
- Une méthode `afficher()` qui affiche les informations dans ce format :

**Sortie attendue :**
```
Titre : Le Petit Prince | Auteur : Antoine de Saint-Exupéry | Pages : 96
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```



# **Partie 2 – Héritage et polymorphisme (20 points)**

### **Question 2 (5 points)**  
Créer une classe `Media` avec une méthode `jouer()` qui affiche :

**Sortie attendue :**
```
Lecture d’un média générique
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

# **Question 3 (7 points)**  
Créer deux classes qui héritent de `Media` :  
- `Musique` : la méthode `jouer()` affiche :  
  ```
  Lecture d’un fichier audio
  ```
- `Film` : la méthode `jouer()` affiche :  
  ```
  Lecture d’un film vidéo
  ```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

# **Question 4 (8 points)**  
Créer une fonction `lancer_lecture(media)` qui prend un objet de type `Media` ou ses sous-classes et appelle `jouer()`.

**Exemple d’utilisation :**
```python
m1 = Musique()
f1 = Film()
lancer_lecture(m1)
lancer_lecture(f1)
```

**Sortie attendue :**
```
Lecture d’un fichier audio  
Lecture d’un film vidéo
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```



# **Partie 3 – Classes abstraites (20 points)**

# **Question 5 (5 points)**  
Créer une classe abstraite nommée `Employe` contenant une méthode abstraite `calcul_salaire()`.

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

# **Question 6 (10 points)**  
Créer deux classes concrètes qui héritent de `Employe` :

- `EmployeHoraire` avec les attributs `taux_horaire`, `heures_travaillees`  
- `EmployePermanent` avec l’attribut `salaire_fixe`  
Chaque classe doit implémenter `calcul_salaire()`.

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

# **Question 7 (5 points)**  
Créer une fonction `afficher_salaire(employe)` qui affiche le salaire, quelle que soit la classe d’employé.

**Exemple d’utilisation :**
```python
e1 = EmployeHoraire(20, 35)
e2 = EmployePermanent(3000)
afficher_salaire(e1)
afficher_salaire(e2)
```

**Sortie attendue :**
```
Salaire : 700  
Salaire : 3000
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```



# **Partie 4 – Encapsulation avec `@property` (15 points)**

### **Question 8 (15 points)**  
Créer une classe `CompteBancaire` avec :  
- Un attribut privé `_solde`  
- Une propriété `solde` pour accéder au solde  
- Un setter qui interdit toute valeur négative (affiche un message d’erreur)

**Exemple d’utilisation :**
```python
c = CompteBancaire(100)
print(c.solde)
c.solde = 200
print(c.solde)
c.solde = -50
```

**Sortie attendue :**
```
100  
200  
Erreur : le solde ne peut pas être négatif.
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```



# **Partie 5 – Méthodes supplémentaires (obligatoire) (15 points)**

### **Question 9 (15 points)**  
Ajouter à la classe `CompteBancaire` :

- `deposer(montant)` : ajoute le montant au solde  
- `retirer(montant)` : retire le montant seulement si le solde est suffisant  
  Sinon, afficher un message d’erreur.

**Exemple d’utilisation :**
```python
c = CompteBancaire(100)
c.deposer(50)
print(c.solde)
c.retirer(30)
print(c.solde)
c.retirer(200)
```

**Sortie attendue :**
```
150  
120  
Fonds insuffisants
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```



# **Partie 6 – Mise en œuvre complète (obligatoire) (20 points)**

### **Question 10 (20 points)**  
Créer un mini-système contenant :

- Une classe abstraite `Animal`  
- Deux classes filles : `Chien` et `Chat`  
- Un attribut `__age` avec `@property` + validation (âge ≥ 0)  
- Une méthode `parler()` décorée avec un décorateur `logger` qui affiche "Appel de la méthode : parler"

**Exemple d’utilisation :**
```python
chien = Chien("Rex", 5)
chat = Chat("Minou", 3)
chien.parler()
chat.parler()
```

**Sortie attendue :**
```
Appel de la méthode : parler  
Le chien aboie. Il a 5 ans.  
Le chat miaule. Il a 3 ans.
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

