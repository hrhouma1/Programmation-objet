#  **Exercice 1 : Lire un fichier ligne par ligne et afficher les noms**

###  Fichier à créer : `prenoms.txt`

Copiez-collez ce contenu dans un fichier `prenoms.txt` :

```
Alice
Benoit
Carla
David
Emma
Farid
Gabrielle
Hugo
Inès
Jules
```

###  Objectif :
Lire chaque prénom et l’afficher avec la phrase :  
**"Bonjour, [prénom] !"**

###  Résultat attendu :

```
Bonjour, Alice !
Bonjour, Benoit !
...
Bonjour, Jules !
```














<br/>

## **Correction – Exercice 1 : Lire un fichier ligne par ligne et afficher les noms**

**Objectif** : Lire chaque prénom du fichier `prenoms.txt` et afficher une salutation personnalisée.

```python
with open('prenoms.txt', 'r') as fichier:
    for ligne in fichier:
        nom = ligne.strip()
        print(f"Bonjour, {nom} !")
```

<br/>














#  **Exercice 2 : Compter les lignes contenant une certaine lettre**

###  Fichier à créer : `villes.txt`

Copiez-collez ce contenu dans un fichier `villes.txt` :

```
Paris
Lyon
Marseille
Toulouse
Nice
Nantes
Strasbourg
Montpellier
Bordeaux
Lille
```

###  Objectif :
Compter combien de villes contiennent la lettre **"o"** (minuscule uniquement).

###  Résultat attendu :

```
Nombre de villes contenant 'o' : 4
```

(ici : Toulouse, Bordeaux, Montpellier, Lyon)







<br/>



## **Correction – Exercice 2 : Compter les lignes contenant une certaine lettre**

**Objectif** : Compter les villes contenant la lettre "o".

```python
compteur = 0

with open('villes.txt', 'r') as fichier:
    for ligne in fichier:
        ville = ligne.strip()
        if 'o' in ville:
            compteur += 1

print(f"Nombre de villes contenant 'o' : {compteur}")
```

<br/>











#  **Exercice 3 : Ajouter des notes dans un fichier**

###  Objectif :
Créer un fichier `notes.txt` et y écrire les lignes suivantes (à l’aide de Python) :

```
Mathématiques : 17
Physique : 14
Informatique : 18
Français : 12
Anglais : 16
```

Ensuite, relire le fichier et afficher uniquement les matières avec une note supérieure ou égale à 15.

###  Résultat attendu :

```
Mathématiques : 17
Informatique : 18
Anglais : 16
```







<br/>



## **Correction – Exercice 3 : Ajouter des notes dans un fichier et filtrer**

**Étape 1** : Écrire les notes dans le fichier `notes.txt`.

```python
with open('notes.txt', 'w') as fichier:
    fichier.write("Mathématiques : 17\n")
    fichier.write("Physique : 14\n")
    fichier.write("Informatique : 18\n")
    fichier.write("Français : 12\n")
    fichier.write("Anglais : 16\n")
```

**Étape 2** : Lire le fichier et afficher les matières avec une note ≥ 15.

```python
with open('notes.txt', 'r') as fichier:
    for ligne in fichier:
        ligne = ligne.strip()
        if ligne:
            partie = ligne.split(":")
            if len(partie) == 2:
                note = int(partie[1].strip())
                if note >= 15:
                    print(ligne)
```


<br/>















#  **Exercice 4 : Lecture, transformation et écriture dans un nouveau fichier**

###  Fichier à créer : `animaux.txt`

Copiez-collez ce contenu dans un fichier `animaux.txt` :

```
chat
chien
lapin
oiseau
cheval
poisson
singe
tigre
renard
zèbre
```

### Objectif :
Lire chaque mot du fichier `animaux.txt`, le convertir en MAJUSCULES, et écrire le résultat dans un nouveau fichier `animaux_maj.txt`.

### Contenu de `animaux_maj.txt` attendu :

```
CHAT
CHIEN
LAPIN
OISEAU
CHEVAL
POISSON
SINGE
TIGRE
RENARD
ZÈBRE
```







<br/>


## **Correction – Exercice 4 : Lecture, transformation et écriture**

**Objectif** : Lire un fichier de mots et écrire leur version en majuscules dans un nouveau fichier.

```python
with open('animaux.txt', 'r') as entree, open('animaux_maj.txt', 'w') as sortie:
    for ligne in entree:
        mot = ligne.strip()
        mot_majuscule = mot.upper()
        sortie.write(mot_majuscule + '\n')
```

<br/>












#  **Exercice 5 : Calculer la moyenne à partir d’un fichier CSV simple**

###  Fichier à créer : `eleves.csv`

Copiez-collez ce contenu dans un fichier `eleves.csv` :

```
Nom,Note
Ali,12
Sarah,15
John,9
Nina,18
Marc,13
Laura,17
```

###  Objectif :
- Lire le fichier CSV
- Calculer la **moyenne des notes**
- Afficher :  
  `Moyenne générale : [valeur]`

###  Résultat attendu :

```
Moyenne générale : 14.0
```




<br/>

## **Correction – Exercice 5 : Calcul de moyenne depuis un fichier CSV**

**Objectif** : Lire un fichier CSV simple, extraire les notes et calculer la moyenne.

```python
total = 0
nb_eleves = 0

with open('eleves.csv', 'r') as fichier:
    next(fichier)  # Ignorer l'en-tête
    for ligne in fichier:
        ligne = ligne.strip()
        if ligne:
            nom, note_str = ligne.split(",")
            note = float(note_str)
            total += note
            nb_eleves += 1

if nb_eleves > 0:
    moyenne = total / nb_eleves
    print(f"Moyenne générale : {moyenne:.1f}")
else:
    print("Aucune note à traiter.")
```

<br/>
