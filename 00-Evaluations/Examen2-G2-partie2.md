# **Examen 2 – Programmation Orientée Objet en Python**  
**Date :** Lundi 31 avril  
**Barème total : 100 points**

---

# **Partie 1 – Classes de base (10 points)**

### **Question 1 (10 points)**  
Créer une classe nommée `Film` avec les caractéristiques suivantes :  
- Attributs : `titre` (str), `realisateur` (str), `duree` (int, en minutes)  
- Un constructeur permettant d’initialiser ces trois attributs  
- Une méthode `afficher()` qui affiche les informations dans ce format :

**Sortie attendue :**
```
Titre : Inception | Réalisateur : Christopher Nolan | Durée : 148 minutes
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

# **Partie 2 – Héritage et polymorphisme (20 points)**

### **Question 2 (5 points)**  
Créer une classe `Appareil` avec une méthode `utiliser()` qui affiche :

**Sortie attendue :**
```
Utilisation d’un appareil générique
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

### **Question 3 (7 points)**  
Créer deux classes qui héritent de `Appareil` :  
- `Ordinateur` : la méthode `utiliser()` affiche :  
  ```
  Utilisation d’un ordinateur portable
  ```
- `Smartphone` : la méthode `utiliser()` affiche :  
  ```
  Utilisation d’un smartphone moderne
  ```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

### **Question 4 (8 points)**  
Créer une fonction `demarrer_utilisation(appareil)` qui prend un objet de type `Appareil` ou ses sous-classes et appelle `utiliser()`.

**Exemple d’utilisation :**
```python
a1 = Ordinateur()
a2 = Smartphone()
demarrer_utilisation(a1)
demarrer_utilisation(a2)
```

**Sortie attendue :**
```
Utilisation d’un ordinateur portable  
Utilisation d’un smartphone moderne
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

# **Partie 3 – Classes abstraites (20 points)**

### **Question 5 (5 points)**  
Créer une classe abstraite nommée `Vehicule` contenant une méthode abstraite `calcul_vitesse()`.

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

### **Question 6 (10 points)**  
Créer deux classes concrètes qui héritent de `Vehicule` :

- `Voiture` avec les attributs `distance` et `temps`  
- `Moto` avec les mêmes attributs  
Chaque classe doit implémenter `calcul_vitesse()` (vitesse = distance / temps)

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

### **Question 7 (5 points)**  
Créer une fonction `afficher_vitesse(vehicule)` qui affiche la vitesse, quelle que soit la classe de véhicule.

**Exemple d’utilisation :**
```python
v1 = Voiture(150, 2)
v2 = Moto(100, 1)
afficher_vitesse(v1)
afficher_vitesse(v2)
```

**Sortie attendue :**
```
Vitesse : 75.0 km/h  
Vitesse : 100.0 km/h
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

# **Partie 4 – Encapsulation avec `@property` (15 points)**

### **Question 8 (15 points)**  
Créer une classe `Thermometre` avec :  
- Un attribut privé `_temperature`  
- Une propriété `temperature` pour accéder à la température  
- Un setter qui interdit les températures inférieures à -273 (zéro absolu)

**Exemple d’utilisation :**
```python
t = Thermometre(20)
print(t.temperature)
t.temperature = 30
print(t.temperature)
t.temperature = -300
```

**Sortie attendue :**
```
20  
30  
Erreur : température invalide (inférieure au zéro absolu).
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

# **Partie 5 – Méthodes supplémentaires (obligatoire) (15 points)**

### **Question 9 (15 points)**  
Ajouter à la classe `Thermometre` :

- `augmenter(degre)` : augmente la température  
- `diminuer(degre)` : diminue la température uniquement si la température finale ≥ -273, sinon afficher une erreur

**Exemple d’utilisation :**
```python
t = Thermometre(10)
t.augmenter(15)
print(t.temperature)
t.diminuer(5)
print(t.temperature)
t.diminuer(300)
```

**Sortie attendue :**
```
25  
20  
Erreur : température invalide (inférieure au zéro absolu).
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

---

# **Partie 6 – Mise en œuvre complète (obligatoire) (20 points)**

### **Question 10 (20 points)**  
Créer un mini-système contenant :

- Une classe abstraite `Utilisateur`  
- Deux classes filles : `Admin` et `Invite`  
- Un attribut privé `__nom` avec `@property` + validation (nom non vide)  
- Une méthode `connexion()` décorée avec un décorateur `logger` qui affiche "Connexion détectée"

**Exemple d’utilisation :**
```python
admin = Admin("Alice")
invite = Invite("Bob")
admin.connexion()
invite.connexion()
```

**Sortie attendue :**
```
Connexion détectée  
Admin Alice connecté  
Invite Bob connecté
```

```python
...........................................................
...........................................................
...........................................................
...........................................................
...........................................................
```

