# TRAVAIL PRATIQUE – MANIPULATION DE FICHIERS ET GESTION AVANCÉE AVEC GIT  

**Durée** : 3 semaines  
**Nom de l'étudiant** : _______________________________ Groupe : ___________  


<br/>

### Consignes générales importantes :

- **Chaque modification doit être suivie exactement des commandes Git suivantes dans l'ordre :**  
  1. `git branch nom_branche`  
  2. `git checkout nom_branche`  
  3. `git add chemin/fichier_modifié`  
  4. `git commit -m "Message clair expliquant la modification"`  
  5. Retour sur `main` : `git checkout main`  
  6. Fusion de branche : `git merge nom_branche`  
  7. Suppression branche fusionnée : `git branch -d nom_branche`

- Chaque commande Git utilisée doit être clairement inscrite dans `git_commands.txt`.

- Tous les scripts Python doivent être dans le dossier `scripts/`.

- Tous les fichiers de données générés doivent être placés dans le dossier `data/`.


<br/>

## 0. INITIALISATION DU PROJET

**Emplacement :** à la racine de votre espace de travail.

Complétez les commandes suivantes exactement :

```bash
Commande 1 : _______________________________________ # mkdir tp_fichiers_git
Commande 2 : _______________________________________ # cd tp_fichiers_git
Commande 3 : _______________________________________ # git init
Commande 4 : _______________________________________ # Créer README.md (à la racine)
Commande 5 : _______________________________________ # git add README.md
Commande 6 : _______________________________________ # git commit -m "Initialisation du projet"
```


<br/>

## 1. FICHIERS TEXTE (.txt)

### 1.1 Écriture sans utiliser `with open()`  

**Branche Git à créer :** `txt-sans-with`

**Emplacement :**  
- Script : `scripts/ecriture_sans_with.py`  
- Fichier : `data/journal.txt`

- Écrivez dans le fichier (`journal.txt`) sans utiliser `with open()` :
```
Jour 1 : Introduction
Jour 2 : Variables
Jour 3 : Conditions
```

```python
# Écrire ici le script Python :
```

**Commandes Git à effectuer :** (`branch`, `checkout`, `add`, `commit`, retour sur `main`, `merge`, `branch -d`)


<br/>

### 1.2 Réécriture avec utilisation de `with open()`

**Branche Git à créer :** `txt-avec-with`

**Emplacement :**  
- Script : `scripts/ecriture_avec_with.py`
- Fichier modifié : `data/journal.txt`

- Réécrivez les mêmes lignes précédentes avec `with open()`.  
- Ajoutez ensuite une ligne en mode `"a"` : `Jour 4 : Boucles`

```python
# Écrire ici le script Python :
```

**Commandes Git à effectuer** (complètes comme en 1.1)


<br/>

### 1.3 Lecture numérotée du fichier texte

**Branche Git à créer :** `txt-lecture`

**Emplacement :**  
- Script : `scripts/lecture_journal.py`

- Affichez chaque ligne de `journal.txt` avec le numéro de ligne :

```
Ligne 1 : Jour 1 : Introduction
Ligne 2 : Jour 2 : Variables
Ligne 3 : Jour 3 : Conditions
Ligne 4 : Jour 4 : Boucles
```

```python
# Écrire ici le script Python :
```

**Commandes Git à effectuer** (complètes comme précédemment)


<br/>

## 2. FICHIERS CSV (.csv)

### 2.1 Création CSV avec `csv.writer()`

**Branche Git à créer :** `csv-creation`

**Emplacement :**  
- Script : `scripts/creation_csv.py`
- Fichier généré : `data/notes.csv`

Créez un fichier CSV contenant exactement :

```
Nom,Note
Alice,90
Bob,72
Chloe,88
```

```python
# Écrire ici le script Python :
```

**Commandes Git à effectuer** (complètes)


<br/>

### 2.2 Lecture brute du CSV (texte brut)

**Branche Git à créer :** `csv-brut`

**Emplacement :**  
- Script : `scripts/lecture_brute.py`

- Lisez et affichez simplement le contenu du fichier CSV comme texte brut avec `open()`.

```python
# Écrire ici le script Python :
```

**Commandes Git à effectuer** (complètes)


<br/>

### 2.3 Lecture structurée CSV (`csv.reader()`)

**Branche Git à créer :** `csv-reader`

**Emplacement :**  
- Script : `scripts/lecture_structurée.py`

- Lisez le CSV et affichez clairement sous la forme suivante :

```
Alice a obtenu 90
Bob a obtenu 72
Chloe a obtenu 88
```

```python
# Écrire ici le script Python :
```

**Commandes Git à effectuer** (complètes)


<br/>

### 2.4 Conflit Git volontaire à créer

- Branche `ajout-etudiant-1` (créée depuis `main`)  
  Ajoutez `David,95` dans `notes.csv` puis committez.

- Branche `ajout-etudiant-2` (créée depuis `main`)  
  Ajoutez `Emma,91` dans `notes.csv` puis committez.

- Fusionnez ces deux branches dans `main` pour provoquer un conflit.  
  Résolvez le conflit manuellement et expliquez votre résolution dans `analyse.txt`.

**Commandes Git à effectuer précisément :** `branch`, `checkout`, `add`, `commit`, `checkout main`, `merge`, résoudre conflit, `branch -d`


<br/>

## 3. FICHIERS JSON (.json)

### 3.1 Création JSON

**Branche Git à créer :** `json-creation`

**Emplacement :**  
- Fichier JSON créé : `data/produits.json`

Créez exactement :

```json
{
  "produits": [
    {"nom": "Clé USB", "prix": 12.5},
    {"nom": "Stylo", "prix": 2.0}
  ]
}
```

**Commandes Git à effectuer** (complètes)


<br/>

### 3.2 Conflit Git volontaire JSON à créer

- Branche `json-promo` (depuis main) : Ajoutez `"promo": true` à `"Clé USB"`. Committez.  
- Branche `json-prix` (depuis main) : Changez `"prix"` de `"Clé USB"` à `10.0`. Committez.

- Fusionnez ces deux branches dans `main`.  
- Résolvez le conflit manuellement en conservant les deux changements.  
- Documentez clairement votre résolution dans `analyse.txt`.


<br/>

## 4. FICHIERS NUMPY (.csv avec numpy)

### 4.1 Sauvegarde tableau NumPy

**Branche Git à créer :** `numpy-save`

**Emplacement :**  
- Script : `scripts/save_numpy.py`
- Fichier généré : `data/fibonacci.csv`

- Sauvegardez le tableau `[1, 2, 3, 5, 8]` avec `np.savetxt()`.


<br/>

### 4.2 Chargement et analyse tableau NumPy

**Branche Git à créer :** `numpy-load-analyse`

**Emplacement :**  
- Script : `scripts/load_analyse_numpy.py`

- Chargez `fibonacci.csv`, puis affichez la moyenne, le minimum, le maximum.


<br/>

## 5. QUESTIONS FINALES (`analyse.txt` à compléter précisément)

1. Pourquoi est-il conseillé d'utiliser `with open()` plutôt que `open()/close()` ?
Réponse : ______________________________________________________

2. Expliquez précisément comment vous avez résolu les conflits Git créés dans ce TP :
Réponse : ______________________________________________________

3. Donnez la commande Git pour restaurer un fichier supprimé accidentellement :
Réponse : ______________________________________________________


<br/>

## 6. VÉRIFICATION FINALE

Exécutez cette commande exactement dans votre dépôt à la fin du TP :

```bash
git log --oneline --graph
```

Copiez le résultat exact dans l'espace suivant :

```
# Collez ici le résultat exact de git log --oneline --graph :
```

<br/>

## 7. LIVRABLES À FOURNIR EXACTEMENT

- Dossier complet du projet (`tp_fichiers_git.zip`) avec dossier `.git`.
- Dossiers complets : `scripts/`, `data/`.
- Fichier `git_commands.txt` complet.
- Fichier `analyse.txt` intégralement rempli.



**Vérifiez soigneusement chaque étape avant remise du TP.**
