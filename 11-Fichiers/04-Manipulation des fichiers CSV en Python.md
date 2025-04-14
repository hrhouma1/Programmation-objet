# Manipulation des fichiers CSV en Python

## 1. Exemples de fichiers CSV avec séparateurs variés

### 1.1. Introduction

Un fichier CSV est un fichier texte utilisé pour stocker des données sous forme de tableau.  
Chaque ligne représente un enregistrement, et chaque colonne est séparée par un caractère, souvent une virgule ou un point-virgule.  
Les fichiers CSV sont largement utilisés pour l’échange de données entre systèmes, notamment entre bases de données, tableurs (comme Excel) et programmes.  
Ils sont simples à lire, à éditer et à générer automatiquement par des scripts en Python, Bash, etc.  
Grâce à leur format universel, les fichiers CSV sont un standard courant pour l’import et l’export de données structurées.


### 1.2. Exemple de fichier csv

##### Contenu du fichier `employes.csv` :**

```
ID,Nom,Service,DateEmbauche,Salaire
1,Dupont Jean,Informatique,2020-03-15,45000
2,Martin Claire,RH,2018-07-01,42000
3,Bernard Luc,Finance,2019-11-23,47000
4,Lemoine Sophie,Marketing,2021-01-10,39000
5,Girard Alain,Informatique,2017-09-30,50000
6,Morel Elise,RH,2022-04-12,41000
7,Petit Paul,Finance,2016-12-05,55000
8,Roux Nathalie,Informatique,2015-06-20,60000
9,Henry Lucas,Marketing,2020-10-03,43000
10,Blanc Julie,RH,2019-08-27,40000
11,Faure Marc,Finance,2018-02-14,53000
12,Perrot Chloé,Marketing,2021-05-18,37000
13,Adam Sylvain,Informatique,2022-08-08,48000
14,Chevalier Laura,RH,2017-11-29,44000
15,Noel Thierry,Finance,2023-01-01,46000
```

###  **Question 1 : Quel est le séparateur utilisé dans ce fichier CSV ?**

**Indice** :  
Observe les caractères qui séparent les différentes colonnes (ID, Nom, Service, etc.) dans chaque ligne.  
Regarde par exemple cette ligne :

```
1,Dupont Jean,Informatique,2020-03-15,45000
```

**Réponse** :  
Le séparateur est **la virgule** `,`.  
C’est ce qui permet de séparer chaque **champ** (ou colonne) dans un fichier CSV (Comma-Separated Values = valeurs séparées par des virgules).



### **Question 2 : Quel est le schéma (ou "schema") de ce fichier CSV ?**

**Indice** :  
Le schéma représente la structure du fichier, c’est-à-dire la liste et l’ordre des **colonnes** avec leurs **types de données**.

**Réponse** :  
Voici le schéma de ce fichier CSV :

| Nom de la colonne | Type de données       | Description                                 |
|-------------------|------------------------|---------------------------------------------|
| ID                | entier (`int`)         | Identifiant unique de l'employé             |
| Nom               | chaîne (`string`)      | Nom complet de l'employé                    |
| Service           | chaîne (`string`)      | Département où travaille l'employé          |
| DateEmbauche      | date (`YYYY-MM-DD`)    | Date d'embauche de l'employé               |
| Salaire           | entier (`int`)         | Salaire annuel brut en dollars ($CAD)       |





### 1.3. Autres exemples de fichier csv

| Fichier | Contenu | Séparateur |
|--------|---------|------------|
| `eleves.csv` | `Nom,Prénom,Note`<br>`Martin,Julie,15` | Virgule `,` |
| `produits.csv` | `ID;Nom;Prix`<br>`1;Stylo;2.5` | Point-virgule `;` |
| `emplois.csv` | `Nom\tPoste\tSalaire`<br>`Tremblay\tAnalyste\t45000` | Tabulation `\t` |
| `comptes.csv` | `Utilisateur|MotDePasse|Email`<br>`admin|1234|admin@mail.com` | Barre verticale `|` |
| `regions.csv` | `Code Région:Nom Région`<br>`QC:Québec` | Deux-points `:` |

---

## 2. Quiz : Identifiez le séparateur utilisé

1. `ID;Nom;Prix`  
   Séparateur : `________`

2. `Nom,Prénom,Age`  
   Séparateur : `________`

3. `Code Région:Nom Région`  
   Séparateur : `________`

4. `Utilisateur|MotDePasse|Email`  
   Séparateur : `________`

5. `Nom\tPoste\tSalaire`  
   Séparateur : `________`  
   *(indice : cette ligne vient d'un fichier avec tabulation)*

---

## 3. Lecture manuelle d’un fichier CSV (sans la bibliothèque csv)

### Exemple avec `eleves.csv`
Contenu :
```
Nom,Prénom,Note
Martin,Julie,15
Durand,Paul,12
```

```python
# Lecture manuelle
with open("files/eleves.csv", "r", encoding="utf-8") as f:
    for ligne in f:
        print(ligne.strip())  # .strip() pour enlever les \n
```

---

## 4. Lecture avec `csv.reader`

```python
import csv

with open("files/eleves.csv", newline='', encoding="utf-8") as f:
    lecteur = csv.reader(f, delimiter=',')
    for ligne in lecteur:
        print(ligne)
```

### Résultat :
```
['Nom', 'Prénom', 'Note']
['Martin', 'Julie', '15']
['Durand', 'Paul', '12']
```

---

## 5. Lecture avec `csv.DictReader`

```python
import csv

with open("files/eleves.csv", newline='', encoding="utf-8") as f:
    lecteur = csv.DictReader(f, delimiter=',')
    for ligne in lecteur:
        print(f"{ligne['Prénom']} {ligne['Nom']} a obtenu {ligne['Note']}/20")
```

---

## 6. Lecture avec un séparateur personnalisé

### Exemple avec `produits.csv` (séparateur `;`)
```python
import csv

with open("files/produits.csv", newline='', encoding="utf-8") as f:
    lecteur = csv.reader(f, delimiter=';')
    for ligne in lecteur:
        print(ligne)
```

---

## 7. Écriture manuelle dans un fichier CSV

```python
donnees = [
    ["Nom", "Prénom", "Âge"],
    ["Doe", "John", 25],
    ["Smith", "Jane", 30]
]

with open("files/nouveau_fichier.csv", "w", encoding="utf-8", newline='') as f:
    for ligne in donnees:
        f.write(",".join(map(str, ligne)) + "\n")
```

---

## 8. Écriture avec `csv.writer`

```python
import csv

donnees = [
    ["Nom", "Prénom", "Âge"],
    ["Doe", "John", 25],
    ["Smith", "Jane", 30]
]

with open("files/nouveau_fichier.csv", "w", newline='', encoding="utf-8") as f:
    writer = csv.writer(f, delimiter=',')
    writer.writerows(donnees)
```

---

## 9. Ajout de lignes (mode append)

```python
import csv

with open("files/eleves.csv", "a", newline='', encoding="utf-8") as f:
    writer = csv.writer(f)
    writer.writerow(["Lemoine", "Sarah", 18])
```

---

## 10. Bonus : Tracer des coordonnées

Fichier `coordonnees.csv` :
```
X,Y
100,100
102,105
104,108
```

```python
import csv
from matplotlib import pyplot as plt

x = []
y = []

with open("files/coordonnees.csv", newline='') as f:
    lecteur = csv.reader(f)
    next(lecteur)  # Ignorer l'entête
    for ligne in lecteur:
        x.append(float(ligne[0]))
        y.append(float(ligne[1]))

plt.scatter(x, y)
plt.title("Coordonnées")
plt.xlabel("X")
plt.ylabel("Y")
plt.show()
```
