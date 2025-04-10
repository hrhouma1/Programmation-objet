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

