
# Table des matières

1. [Code 1 - Vitesse d'exécution d'une liste python comparée à un tableau numpy](#code-1---vitesse-dexécution-dune-liste-python-comparée-à-un-tableau-numpy)
2. [Code 2 - Plus compact](#code-2---plus-compact)
3. [Code 3 - Multiplier des éléments du tableau par 5 en utilisant la librairie numpy](#code-3---multiplier-des-éléments-du-tableau-par-5-en-utilisant-la-librairie-numpy)
4. [Code 4 - Multiplier des éléments d'une liste par 5 sans Numpy](#code-4---multiplier-des-éléments-dune-liste-par-5-sans-numpy)
5. [Code 5 - Nouveau tableau](#code-5---nouveau-tableau)
6. [Code 6 - Tableau avec référence préservée](#code-6---tableau-avec-référence-préservée)
7. [Code 7 - Tableau avec référence préservée](#code-7---tableau-avec-référence-préservée)
8. [Code 8 - Copie d'un tableau](#code-8---copie-dun-tableau)
9. [Code 9 - Création d'un tableau avec arange](#code-9---création-dun-tableau-avec-arange)
10. [Code 10 - Création d'un tableau sur une intervalle](#code-10---création-dun-tableau-sur-une-intervalle)
11. [Code 11 - Création de matrices diagonales identité](#code-11---création-de-matrices-diagonales-identité)
12. [Code 12 - Création d'une matrice diagonale avec des 1 5x5](#code-12---création-dune-matrice-diagonale-avec-des-1-5x5)
13. [Code 13 - Création d'une matrice diagonale avec des valeurs croissantes](#code-13---création-dune-matrice-diagonale-avec-des-valeurs-croissantes)
14. [Code 14 - Création de n éléments de valeur 0](#code-14---création-de-n-éléments-de-valeur-0)
15. [Code 15 - Création de n éléments de valeur 1](#code-15---création-de-n-éléments-de-valeur-1)
16. [Code 16 - Nombre aléatoires entre 0 et 1](#code-16---nombre-aléatoires-entre-0-et-1)
17. [Code 17 - Tableau 1D](#code-17---tableau-1d)
18. [Code 18 - Tableau 3D](#code-18---tableau-3d)
19. [Code 19 - Création avec des fonctions Numpy](#code-19---création-avec-des-fonctions-numpy)
20. [Code 20 - Indexation avec des tranches](#code-20---indexation-avec-des-tranches)
21. [Code 21 - Affichage](#code-21---affichage)
22. [Code 22 - Accéder à des colonnes entière](#code-22---accéder-à-des-colonnes-entière)
23. [Code 23 - Indexation booléenne](#code-23---indexation-booléenne)
24. [Code 24 - Le produit matriciel](#code-24---le-produit-matriciel)
25. [Code 25 - Multiplication terme à terme](#code-25---multiplication-terme-à-terme)
26. [Code 26 - Applatissement pour passer d'un tableau multi-dimension à un tableau unidimensionnel](#code-26---applatissement-pour-passer-dun-tableau-multi-dimension-à-un-tableau-unidimensionnel)
27. [Code 27 - Redimensionnement 1D->ND](#code-27---redimensionnement-1d-nd)
28. [Code 28 - La transposée d'une matrice](#code-28---la-transposée-dune-matrice)
29. [Code 29 - Nombre de dimensions](#code-29---nombre-de-dimensions)
30. [Code 30 - amin et amax](#code-30---amin-et-amax)
31. [Code 31 - Moyenne](#code-31---moyenne)
32. [Code 32 - Moyenne pondérée](#code-32---moyenne-pondérée)
33. [Code 33 - La médiane](#code-33---la-médiane)
34. [Code 34 - La taille d'un tableau](#code-34---la-taille-dun-tableau)




## Code 1 - Vitesse d'exécution d'une liste python comparée à un tableau numpy


```python
import numpy as np
import time

# Créer une grande liste et un tableau NumPy
n = 1000000
lst = list(range(n))  # une liste
arr = np.arange(n)    # un tableau NumPy

# Temps pour la multiplication d'une liste Python
start = time.time()
for i in range(len(lst)):
    lst[i] *= 2
print("Temps en secondes pour la liste :", time.time() - start)

# Temps pour la multiplication d'un tableau NumPy
start = time.time()
arr = arr * 2
print("Temps en secondes pour le tableau NumPy :", time.time() - start)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 2 - Plus compact


```python
import sys

lst = list(range(1000))
arr = np.arange(1000)

print("Taille de la liste :", sys.getsizeof(lst), "octets")
print("Taille du tableau NumPy :", arr.nbytes, "octets")
```
[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 3 - Multiplier des éléments du tableau par 5 en utilisant la librairie numpy

```python
tab = np.array([1, 2, 3, 4, 5])
print("Tableau avant multiplication : ", tab)

res = tab * 5
print("Tableau après multiplication : ", res)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 4 - Multiplier des éléments d'une liste par 5 sans Numpy

```python
liste = [1, 2, 3, 4, 5]
print("Liste avant multiplication : ", liste)

res = [element * 5 for element in liste]
print("Liste après multiplication : ", res)
```
[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 5 - Nouveau tableau

```python
animaux = np.array(["Chien", "Chat", "Serpent"])
quantites_lst = [7, 10, 2]
quantites = np.array(quantites_lst)

print("Tableau des animaux :", animaux)
print("Tableau de quantités des animaux :", quantites)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>


## Code 6 - Tableau avec référence préservée

```python
tab1 = np.array(["Chien", "Chat", "Serpent"])
tab2 = np.array(tab1)

tab1[0] = "Poisson"
print("Tableau de base :", tab1)
print("Copie du tableau avec array:", tab2)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>


## Code 7 - Tableau avec référence préservée

```python
tab1 = np.array(["Chien", "Chat", "Serpent"])
tab2 = np.asarray(tab1)

tab2[0] = "Poisson"
print("Tableau de base :", tab1)
print("Copie du tableau avec asarray :", tab2)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 8 - Copie d'un tableau

```python
import numpy as np

tab1 = np.array(["Chien", "Chat", "Serpent"])
tab2 = np.copy(tab1)

tab1[0] = "Poisson"
print("Tableau de base :", tab1) # ['Poisson' 'Chat' 'Serpent']
print("Copie du tableau avec copy :", tab2) # ['Chien' 'Chat' 'Serpent']
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 9 - Création d'un tableau avec arange

```python
tab1 = np.arange(10) # Génère un tableau de 0 (inclus) à 10 (exclus)
print("Tableau avec arange(10) :", tab1) # [0 1 2 3 4 5 6 7 8 9]

tab2 = np.arange(10, 20) # Génère un tableau de 10 (inclus) à 20 (exclus)
print("Tableau avec arange(10, 20) :", tab2) # [10 11 12 13 14 15 16 17 18 19]

# Génère un tableau de 4 (inclus) à 10 (exclus) avec pas de 2
tab3 = np.arange(4, 10, 2)
print("Tableau avec arange(4, 10, 2) :", tab3) # [4 6 8]
```
[Retour 🔙 à la table des matières](#table-des-matières)
<br/>


## Code 10 - Création d'un tableau sur une intervalle

```python
# Génère un tableau réparti entre 0 et 10 inclus avec 5 éléments
tab1 = np.linspace(0, 10, 5)
print("Tableau avec linspace(0, 10, 5) :", tab1) # [0. 2.5 5. 7.5 10.]

# Génère un tableau réparti entre 0 et 1 inclus avec 11 éléments
tab2 = np.linspace(0, 1, 11)
print("Tableau avec linspace(0, 1, 11) :", tab2)
# [0. 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.]

# Génère un tableau réparti entre 1 et 0 (inversé) avec 11 éléments
tab3 = np.linspace(1, 0, 11)
print("Tableau avec linspace(1, 0, 11) :", tab3)
# [1. 0.9 0.8 0.7 0.6 0.5 0.4 0.3 0.2 0.1 0.]
```


[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 11 - Création de matrices diagonales identité

```python
# Création d'une matrice diagonale avec des 1 3x3.
tab1 = np.eye(3)
print(tab1)
'''
[[1 0 0]
 [0 1 0]
 [0 0 1]]
'''
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 12 - Création d'une matrice diagonale avec des 1 5x5.

```python
tab2 = np.eye(5)
print(tab2)
'''
[[1 0 0 0 0]
 [0 1 0 0 0]
 [0 0 1 0 0]
 [0 0 0 1 0]
 [0 0 0 0 1]]
'''
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 13 - Création d'une matrice diagonale avec des valeurs croissantes

```python
valeurs = np.arange(1, 6)  # Par exemple, valeurs de 1 à 5

# Créer une matrice diagonale avec ces valeurs
matrice_diagonale = np.diag(valeurs)

# Afficher la matrice
print(matrice_diagonale)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 14 - Création de n éléments de valeur 0

```python
import numpy as np

tab1 = np.zeros(3)
print(tab1) # [0. 0. 0.]

tab2 = np.zeros(10)
print(tab2) # [0. 0. 0. 0. 0. 0. 0. 0. 0. 0.]
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>


## Code 15 - Création de n éléments de valeur 1

```python
tab1 = np.ones(3)
print(tab1) # [1. 1. 1.]

tab2 = np.ones(10)
print(tab2) # [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 16 - Nombre aléatoires entre 0 et 1

```python

tab1 = np.random.random(3)
print(tab1)

tab2 = np.random.random(10)
print(tab2)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 17 - Tableau 1D

```python
tab_1d = np.array([1, 2, 3, 4, 5, 6])
print(tab_1d)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 18 - Tableau 3D

```python
tab_3d = np.array([
    [
        [111, 112, 113],
        [121, 122, 123],
        [131, 132, 133]
    ],
    [
        [211, 212, 213],
        [221, 222, 223],
        [231, 232, 233]
    ],
    [
        [311, 312, 313],
        [321, 322, 323],
        [331, 332, 333]
    ]
])
print(tab_3d)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 19 - Création avec des fonctions Numpy

```python
import numpy as np

# 1. Tableau 2D rempli de zéros
tableau_zeros = np.zeros((3, 4))  # 3 lignes, 4 colonnes
print("Rempli de zéros (3x4) :\n", tableau_zeros)
print("==================================================")

# 2. Tableau 3D rempli de 1
tableau_ones = np.ones((2, 2, 3))  # 2 matrices, 2 lignes, 3 colonnes
print("\nRempli de 1 (2x2x3) :\n", tableau_ones)
print("==================================================")

# 3. Tableau 2D avec des valeurs aléatoires uniformes
tableau_random_uniform = np.random.rand(4, 5)  # 4 lignes, 5 colonnes
print("\nValeurs aléatoires uniformes (4x5) :\n", tableau_random_uniform)
print("==================================================")

# 4. Tableau 1D avec des valeurs aléatoires
tableau_random_1d = np.random.random(10)  # 10 éléments
print("\nValeurs aléatoires (10 éléments) :\n", tableau_random_1d)
print("==================================================")

# 5. Tableau 2D vide (non initialisé)

tableau_empty = np.empty((2, 3))  # 2 lignes, 3 colonnes
print("Vide (2x3) :\n", tableau_empty)
print("==================================================")

# 6. Afficher la forme, la taille et le type des tableaux
print("Propriétés des tableaux :")
for tableau in [tableau_zeros, tableau_ones, tableau_random_uniform, tableau_random_1d, tableau_empty]:
    print(f"Shape: {tableau.shape}, Taille: {tableau.size}")
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 20 - Indexation avec des tranches

```python
import numpy as np

# Création du tableau de coordonnées (colonne 1 : X, colonne 2 : Y)
tab = np.array([
    [ 0, 2],
    [ 2, 2],
    [ 4, 4],
    [ 6, 6],
    [ 8, 7],
    [10, 7],
    [12, 8]
])
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 21 - Affichage

```python
print(tab)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 22 - Accéder à des colonnes entière

```python
x = tab[:, 0] # Obtient toutes les rangées (:), mais seulement la colonne 0
y = tab[:, 1] # Obtient toutes les rangées (:), mais seulement la colonne 1

print("Coordonnées X")
print(x)
print("Coordonnées Y")
print(y)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 23 - Indexation booléenne

```python
import numpy as np

# Créer un tableau
arr = np.array([1, 2, 3, 4, 5, 6])

# Utiliser une condition pour créer un masque
masque = arr > 3  # Renvoie un tableau de booléens
print(masque)  # Output: [False False False  True  True  True]

# Appliquer le masque pour extraire les éléments
elements_filtres = arr[masque]
print(elements_filtres)  # Output: [4 5 6]
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 24 - Le produit matriciel

```python
import numpy as np

# Création de nos deux matrices
tab1 = np.array([[1, 2, 3], [4, 5, 6]])
tab2 = np.array([[7, 8], [9, 10], [11, 12]])

# Affichage de la dimensions de nos deux matrices
print("Matrice 1 :", np.shape(tab1))
print("Matrice 2 :", np.shape(tab2))

tab3 = np.dot(tab1, tab2)
print("Résultat :", tab3)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 25 - Multiplication terme à terme

```python
import numpy as np

# Tableau A
tab_a = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

# Tableau B
tab_b = np.array([
    [4, 1, 2],
    [3, 2, 1]
])

# Tableau A * C
tab_mult = tab_a * tab_b

# Affichage
print("--- Tableau A ---")
print (tab_a)
print("--- Tableau B ---")
print (tab_b)
print("--- Tableau A * B ---")
print (tab_mult)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 26 - Applatissement pour passer d'un tableau multi-dimension à un tableau unidimensionnel

```python
import numpy as np

# Créaction d'un tableau 2x3
tab1 = np.array([[1, 2, 3], [4, 5, 6]])
print(tab1)
'''
[[1 2 3]
 [4 5 6]]
'''
print(np.shape(tab1)) # Affichage de la dimension du tableau

# Aplatissement du tableau
tab2 = np.ravel(tab1)
print(tab2) # [1 2 3 4 5 6]
print(np.shape(tab2)) # Affichage de la dimension du tableau
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 27 - Redimensionnement 1D->ND

```python
import numpy as np

# Création d'un tableau de 6 éléments
tab1 = np.array([1, 2, 3, 4, 5, 6])
print(tab1) # [1 2 3 4 5 6]
print(np.shape(tab1)) # Affichage de la dimension du tableau

# Redimensionnement du tableau en 2x3
tab2 = np.reshape(tab1, (2, 3))
print(tab2)
'''
[[1 2 3]
 [4 5 6]]
'''
print(np.shape(tab2)) # Affichage de la dimension du tableau
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 28 - La transposée d'une matrice

```python
import numpy as np

# Création d'une matrice 3x3
tab1 = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
print(tab1)
'''
[[1 2 3]
 [4 5 6]
 [7 8 9]]
'''

tab_transpo = np.transpose(tab1)
print(tab_transpo)
'''
[[1 4 7]
 [2 5 8]
 [3 6 9]]
'''
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 29 - Nombre de dimensions

```python
import numpy as np

# Créer un tableau 3D
arr = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])

# Vérifier le nombre de dimensions
print("Nombre de dimensions :", arr.ndim)
# Devrait afficher 3 si le tableau est en 3D
print("Les dimensions :", arr.shape)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 30 - amin et amax

```python
import numpy as np

# Exemple avec un tableau 2D
tab_2d = np.array([[3, 7, 5],
                   [8, 2, 1],
                   [4, 9, 6]])

# Trouver la valeur minimale de tout le tableau
min_value = np.amin(tab_2d)
print("Valeur minimale globale :", min_value)  # Output: 1

# Trouver la valeur maximale de tout le tableau
max_value = np.amax(tab_2d)
print("Valeur maximale globale :", max_value)  # Output: 9

# Trouver la valeur minimale par axe (par ligne ou colonne)
print("Min par colonne :", np.amin(tab_2d, axis=0))  # Output: [3 2 1]
print("Min par ligne :", np.amin(tab_2d, axis=1))    # Output: [3 1 4]

# Trouver la valeur maximale par axe (par ligne ou colonne)
print("Max par colonne :", np.amax(tab_2d, axis=0))  # Output: [8 9 6]
print("Max par ligne :", np.amax(tab_2d, axis=1))    # Output: [7 8 9]
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 31 - Moyenne

```python
import numpy as np

# Notes d'étudiants
notes = np.array([85, 90, 75, 60, 95])

# Moyenne arithmétique des notes
mean_value = np.mean(notes)
print("Moyenne arithmétique :", mean_value)  # Output: 81.0
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 32 - Moyenne pondérée

```python
import numpy as np
import numpy as np

# Notes d'étudiants
notes = np.array([85, 90, 75, 60, 95])

# Poids associés aux notes (par exemple, certaines évaluations
#                                   peuvent avoir plus de poids)
poids = np.array([0.1, 0.3, 0.2, 0.2, 0.2])

# Moyenne pondérée des notes
average_value = np.average(notes, weights=poids)
print("Moyenne pondérée :", average_value)  # Output: 81.5
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 33 - La médiane

```python
import numpy as np

# Notes d'étudiants
notes = np.array([85, 90, 75, 60, 95])

# Médiane des notes (note au milieu de l'échantillon)
median_value = np.median(notes)
print("Médiane :", median_value)  # Output: 85.0
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>

## Code 34 - La taille d'un tableau

```python
tab1 = np.array([1, 2, 3, 4, 5])
N = np.shape(tab1)[0] # CALCULEZ LA LONGUEUR DE tab1
print(np.shape(tab1))
# tab2 = np.zeros((N, N))
# print(tab1)
# print(N)
# print(tab2)
```

[Retour 🔙 à la table des matières](#table-des-matières)
<br/>
