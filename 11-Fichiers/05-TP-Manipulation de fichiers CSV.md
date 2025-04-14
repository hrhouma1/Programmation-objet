# TP Python – Manipulation de fichiers CSV

## Objectifs pédagogiques :
- Lire des fichiers CSV avec et sans le module `csv`
- Identifier et gérer les séparateurs
- Extraire, transformer et écrire des données CSV
- Éviter les erreurs courantes (encodage, saut de ligne, séparateur)

---

## Contenu du TP

### Fichiers fournis :
1. `eleves.csv` – Virgule `,`  
2. `produits.csv` – Point-virgule `;`  
3. `emplois.csv` – Tabulation `\t`  
4. `comptes.csv` – Barre verticale `|`  
5. `regions.csv` – Deux-points `:`  

> **Remarque :** Les fichiers doivent être placés dans un dossier `files/` au même niveau que le fichier Python.

---

## Partie 1 – Lecture simple sans `csv`

### Fichier : `files/eleves.csv`  
Contenu :
```
Nom,Prénom,Note
Martin,Julie,15
Durand,Paul,12
Nguyen,Minh,17
```

### Instructions :
1. Ouvrir le fichier avec `open()`
2. Lire ligne par ligne
3. Supprimer le saut de ligne avec `.strip()`
4. Afficher le résultat

### Exemple attendu :
```
Nom,Prénom,Note
Martin,Julie,15
Durand,Paul,12
Nguyen,Minh,17
```


## ✅ Correction Partie 1 – Lecture simple sans `csv`

```python
with open("files/eleves.csv", "r", encoding="utf-8") as f:
    for ligne in f:
        print(ligne.strip())
```



---


## Partie 2 – Lecture avec `csv.reader`

### Fichier : `files/eleves.csv`

### Instructions :
1. Utiliser le module `csv`
2. Créer un objet `csv.reader`
3. Afficher les lignes une par une
4. Afficher chaque ligne comme une **liste Python**

### Exemple attendu :
```
['Nom', 'Prénom', 'Note']
['Martin', 'Julie', '15']
['Durand', 'Paul', '12']
['Nguyen', 'Minh', '17']
```





## ✅ Correction Partie 2 – Lecture avec `csv.reader`

```python
import csv

with open("files/eleves.csv", newline='', encoding="utf-8") as f:
    lecteur = csv.reader(f)
    for ligne in lecteur:
        print(ligne)
```







---

## Partie 3 – Lecture d’un fichier avec séparateur `;`

### Fichier : `files/produits.csv`  
Contenu :
```
ID;Nom;Prix
1;Stylo;2.5
2;Cahier;3.0
3;Trousse;6.5
```

### Instructions :
1. Utiliser `csv.reader` avec `delimiter=';'`
2. Afficher chaque ligne



## ✅ Correction Partie 3 – Lecture avec séparateur `;`

```python
import csv

with open("files/produits.csv", newline='', encoding="utf-8") as f:
    lecteur = csv.reader(f, delimiter=';')
    for ligne in lecteur:
        print(ligne)
```





---

## Partie 4 – Lecture avec tabulation `\t`

### Fichier : `files/emplois.csv`  
Contenu (copié avec tabulations) :
```
Nom\tPoste\tSalaire
Tremblay\tAnalyste\t45000
Morin\tDéveloppeur\t52000
```

> **Attention :** Ce fichier contient des **tabulations**, pas des espaces.

### Instructions :
1. Utiliser `delimiter='\t'`
2. Afficher les lignes




## ✅ Correction Partie 4 – Lecture avec tabulation `\t`

```python
import csv

with open("files/emplois.csv", newline='', encoding="utf-8") as f:
    lecteur = csv.reader(f, delimiter='\t')
    for ligne in lecteur:
        print(ligne)
```





---

## Partie 5 – Lecture avec `csv.DictReader`

### Fichier : `files/comptes.csv`  
Contenu :
```
Utilisateur|MotDePasse|Email
admin|admin123|admin@mail.com
user1|abc123|user1@mail.com
```

### Instructions :
1. Utiliser `csv.DictReader` avec `delimiter='|'`
2. Pour chaque ligne, afficher la phrase :
   ```
   L'utilisateur <Utilisateur> a l'email <Email>
   ```

### Exemple attendu :
```
L'utilisateur admin a l'email admin@mail.com
L'utilisateur user1 a l'email user1@mail.com
```

## ✅ Correction Partie 5 – Lecture avec `csv.DictReader`

```python
import csv

with open("files/comptes.csv", newline='', encoding="utf-8") as f:
    lecteur = csv.DictReader(f, delimiter='|')
    for ligne in lecteur:
        print(f"L'utilisateur {ligne['Utilisateur']} a l'email {ligne['Email']}")
```







---

## Partie 6 – Écriture manuelle dans un fichier

### Fichier à créer : `files/resultats.csv`  
Données à écrire :
```python
[["Nom", "Note"], ["Julie", 15], ["Paul", 12], ["Minh", 17]]
```

### Instructions :
1. Écrire manuellement chaque ligne dans le fichier
2. Utiliser `",".join(...)` pour assembler les éléments
3. Vérifier le résultat


## ✅ Correction Partie 6 – Écriture manuelle dans un fichier

```python
donnees = [["Nom", "Note"], ["Julie", 15], ["Paul", 12], ["Minh", 17]]

with open("files/resultats.csv", "w", encoding="utf-8", newline='') as f:
    for ligne in donnees:
        ligne_str = [str(element) for element in ligne]
        f.write(",".join(ligne_str) + "\n")
```





---

## Partie 7 – Écriture avec `csv.writer`

### Même contenu que Partie 6

### Instructions :
1. Utiliser `csv.writer`
2. Appeler `writerow()` pour chaque ligne







## ✅ Correction Partie 7 – Écriture avec `csv.writer`

```python
import csv

donnees = [["Nom", "Note"], ["Julie", 15], ["Paul", 12], ["Minh", 17]]

with open("files/resultats.csv", "w", newline='', encoding="utf-8") as f:
    writer = csv.writer(f, delimiter=',')
    writer.writerows(donnees)
```




---

## Partie 8 – Ajout de données à un fichier existant

### Fichier : `files/eleves.csv`

### Instructions :
1. Ajouter les deux lignes suivantes à la fin du fichier :
   ```
   Lemoine,Sarah,18
   Lopez,Carlos,16
   ```
2. Utiliser le mode `append` (`"a"`)
3. Afficher ensuite tout le fichier pour vérifier



## ✅ Correction Partie 8 – Ajout de lignes à un fichier existant

```python
import csv

with open("files/eleves.csv", "a", newline='', encoding="utf-8") as f:
    writer = csv.writer(f)
    writer.writerow(["Lemoine", "Sarah", 18])
    writer.writerow(["Lopez", "Carlos", 16])
```





---

## Partie 9 – Extraire des colonnes numériques et tracer un graphique

### Fichier : `files/coordonnees.csv`  
Contenu :
```
X,Y
100,100
102,105
104,108
```

### Instructions :
1. Lire les colonnes `X` et `Y` avec `csv.reader`
2. Ignorer l'entête
3. Convertir les valeurs en float
4. Afficher un graphique avec `matplotlib.pyplot.scatter(x, y)`



## ✅ Correction Partie 9 – Tracer des coordonnées

```python
import csv
from matplotlib import pyplot as plt

x = []
y = []

with open("files/coordonnees.csv", newline='', encoding="utf-8") as f:
    lecteur = csv.reader(f)
    next(lecteur)  # Ignorer l'entête
    for ligne in lecteur:
        x.append(float(ligne[0]))
        y.append(float(ligne[1]))

plt.scatter(x, y)
plt.title("Coordonnées")
plt.xlabel("X")
plt.ylabel("Y")
plt.grid(True)
plt.show()
```




   

---

## Partie 10 – Quiz de vérification

### Questions :

1. Quel est le séparateur dans `emplois.csv` ?
2. Pourquoi utilise-t-on `newline=''` dans `open()` avec `csv.reader` ?
3. Qu'est-ce que `csv.DictReader` renvoie ?
4. Quelle est la différence entre :
   - `writer.writerow()`  
   - `writer.writerows()` ?
5. Comment lire correctement un fichier CSV avec des caractères accentués ?


## ✅ Correction Partie 10 – Correction du quiz

1. `emplois.csv` → Séparateur : tabulation `\t`  
2. `newline=''` empêche l'ajout de lignes vides lors de l’écriture (important sous Windows).  
3. `csv.DictReader` renvoie chaque ligne sous forme de dictionnaire avec les clés issues de l'entête.  
4. - `writer.writerow()` écrit **une seule ligne**  
   - `writer.writerows()` écrit **plusieurs lignes à la suite**  
5. Utiliser `encoding="utf-8"` avec `open()`.
