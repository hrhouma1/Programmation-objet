---
# Sommatif 1 - Partie 1
---
📌 **Instructions :**  
- Sélectionnez la bonne réponse pour chaque question.  
- Assurez-vous de bien comprendre chaque concept avant de répondre.  
- Chaque question vaut **10 points**.  

📌 **Barème :**  
- **10 questions** → **100 points** au total.  

---

## **Table des matières**  
- [Question 1 - Syntaxe Python](#question-1)  
- [Question 2 - Types de données](#question-2)  
- [Question 3 - Boucles et conditions](#question-3)  
- [Question 4 - Fonctions](#question-4)  
- [Question 5 - Programmation orientée objet](#question-5)  
- [Question 6 - Modules et importation](#question-6)  
- [Question 7 - Gestion des fichiers](#question-7)  
- [Question 8 - Générateurs et itérateurs](#question-8)  
- [Question 9 - Compréhensions de listes](#question-9)  
- [Question 10 - Optimisation du code](#question-10)  

---

## **Question 1 - Syntaxe Python**  
Quelle est la sortie du code suivant ?  
```python
x = 5
y = "5"
print(x + int(y))
```
   a) `"55"`  
   b) `10`  
   c) `TypeError`  
   d) `5.5`  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 2 - Types de données**  
Quel type de données est retourné par l'expression `type({1, 2, 3})` en Python ?  
   a) `dict`  
   b) `list`  
   c) `set`  
   d) `tuple`  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 3 - Boucles et conditions**  
Quel sera le dernier nombre affiché par cette boucle ?  
```python
for i in range(2, 10, 3):
    print(i)
```
   a) `2`  
   b) `8`  
   c) `10`  
   d) `9`  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 4 - Fonctions**  
Quelle est la sortie du code suivant ?  
```python
def func(a, b=5):
    return a * b

print(func(2))
```
   a) `2`  
   b) `5`  
   c) `10`  
   d) `TypeError`  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 5 - Programmation orientée objet**  
Que fait le décorateur `@staticmethod` dans une classe Python ?  
   a) Rend une méthode indépendante de l’instance et de la classe  
   b) Permet d’accéder aux variables de classe  
   c) Rend une méthode privée  
   d) Supprime la méthode après son premier appel  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 6 - Modules et importation**  
Quelle est la bonne manière d'importer le module `math` et d'utiliser la fonction `sqrt` en Python ?  
   a) `import math; math.sqrt(16)`  
   b) `import sqrt from math; sqrt(16)`  
   c) `math.import(sqrt); sqrt(16)`  
   d) `include math; sqrt(16)`  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 7 - Gestion des fichiers**  
Quel mode d’ouverture permet de lire et d’écrire dans un fichier en Python, **sans écraser son contenu** ?  
   a) `"r"`  
   b) `"w"`  
   c) `"a+"`  
   d) `"x"`  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 8 - Générateurs et itérateurs**  
Quelle est la sortie du code suivant ?  
```python
def my_gen():
    yield 1
    yield 2
    yield 3

g = my_gen()
print(next(g))
print(next(g))
```
   a) `1 2`  
   b) `[1, 2]`  
   c) `1 2 3`  
   d) `GeneratorError`  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 9 - Compréhensions de listes**  
Quelle est la sortie du code suivant ?  
```python
lst = [x**2 for x in range(4)]
print(lst)
```
   a) `[0, 1, 2, 3]`  
   b) `[0, 1, 4, 9]`  
   c) `[1, 4, 9, 16]`  
   d) `[0, 1, 4, 9, 16]`  

[Retour 🔙 à la table des matières](#table-des-matières)  

---

## **Question 10 - Optimisation du code**  
Quelle est la manière la plus efficace d’initialiser une liste de 1000 zéros en Python ?  
   a) `[0] * 1000`  
   b) `list(0 for _ in range(1000))`  
   c) `np.zeros(1000)`  
   d) `{0} * 1000`  

[Retour 🔙 à la table des matières](#table-des-matières)  


---
# Sommatif 1 - Partie 2
---
📌 **Instructions :**  
- Complétez le code Python en remplissant les parties manquantes.  
- Vérifiez que les résultats sont corrects avant de soumettre votre travail.  
- Respectez la syntaxe et utilisez les bonnes fonctions NumPy.

📌 **Barème :**  
- **Exercice 1 : 30 points** (Opérations mathématiques sur des tableaux)  
- **Exercice 2 : 40 points** (Transformation et tri de matrices)  
- **Exercice 3 : 30 points** (Analyse et extraction de données)  

---

## **Exercice 1 - Opérations Mathématiques sur des Tableaux NumPy**  

```python
import numpy as np

# a. Créez un tableau NumPy contenant 15 valeurs aléatoires entre 50 et 150
tab = ...

# b. Remplacez toutes les valeurs supérieures à 100 par leur racine carrée
tab_modifie = ...

# c. Normalisez le tableau entre 0 et 1 (min-max scaling)
tab_normalise = ...

# d. Trouvez la moyenne et la médiane des valeurs normalisées
moyenne = ...
mediane = ...

print("Tableau original :", tab)
print("Tableau modifié :", tab_modifie)
print("Tableau normalisé :", tab_normalise)
print("Moyenne :", moyenne)
print("Médiane :", mediane)
```

---

## **Exercice 2 - Transformation et Tri de Matrices**  

```python
import numpy as np

# a. Créez une matrice 5x5 de nombres entiers aléatoires entre 10 et 99
matrice = ...

# b. Inversez l'ordre des colonnes (de droite à gauche)
matrice_inverse = ...

# c. Appliquez un tri croissant sur chaque ligne de la matrice inversée
matrice_triee = ...

# d. Calculez la somme diagonale de la matrice triée
somme_diagonale = ...

print("Matrice originale :\n", matrice)
print("Matrice inversée :\n", matrice_inverse)
print("Matrice triée :\n", matrice_triee)
print("Somme des éléments diagonaux :", somme_diagonale)
```

---

## **Exercice 3 - Analyse et Extraction de Données**  

```python
import numpy as np

# 1. Création d'un tableau simulant les températures relevées sur 30 jours
temperatures = np.array([15, 17, 16, 14, 20, 22, 25, 19, 18, 21, 23, 26, 27, 24, 28, 30, 29, 32, 31, 33, 35, 36, 34, 37, 38, 40, 39, 41, 42, 43])

# 2. Trouver la température moyenne et maximale du mois
temperature_moyenne = ...
temperature_max = ...

# 3. Identifier les jours où la température a dépassé 30°C
jours_chauds = ...

# 4. Calculer la variation moyenne des températures jour après jour
variation_moyenne = ...

print("Températures du mois :", temperatures)
print("Température moyenne :", temperature_moyenne)
print("Température maximale :", temperature_max)
print("Jours où la température dépasse 30°C :", jours_chauds)
print("Variation moyenne quotidienne :", variation_moyenne)
```

