# Manipulation des fichiers CSV en Python

## 1. Exemples de fichiers CSV avec séparateurs variés

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
