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


➤ Vos commandes Git: 

```python
# Écrire ici vos commandes Git :
................................................................................
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
Jour 4 : Boucles
Jour 5 : Fonctions
Jour 6 : Listes
Jour 7 : Dictionnaires
Jour 8 : Tuples
Jour 9 : Ensembles
Jour 10 : Manipulation de fichiers texte
Jour 11 : Manipulation de fichiers CSV
Jour 12 : Manipulation de fichiers JSON
Jour 13 : NumPy - Sauvegarde de tableaux
Jour 14 : NumPy - Chargement de tableaux
Jour 15 : Graphiques avec matplotlib
Jour 16 : Résolution d'erreurs JSON
Jour 17 : Gestion des exceptions en Python
Jour 18 : Écriture avancée avec format()
Jour 19 : Encodage de fichiers texte
Jour 20 : Conclusion et révision
```




➤ Votre script python : 


```python
# Écrire ici le script Python :
................................................................................
```



**Commandes Git à effectuer :** (`branch`, `checkout`, `add`, `commit`, retour sur `main`, `merge`, `branch -d`)


➤ Vos commandes Git: 

```python
# Écrire ici vos commandes Git :
................................................................................
```

<br/>

### 1.2 Réécriture avec utilisation de `with open()`

**Branche Git à créer :** `txt-avec-with`

**Emplacement :**  
- Script : `scripts/ecriture_avec_with.py`
- Fichier modifié : `data/journal.txt`

- Réécrivez les mêmes lignes précédentes avec `with open()`.  
- Ajoutez ensuite une ligne en mode `"a"` : `Jour 21 : Examen 1`



➤ Votre script python et vos Commandes Git à effectuer :** (`branch`, `checkout`, `add`, `commit`, retour sur `main`, `merge`, `branch -d`)


```python
# Écrire ici le script Python et les commandes Git dans l'ordre :
................................................................................
```




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
....
```



➤ Votre script python et vos Commandes Git à effectuer :** (`branch`, `checkout`, `add`, `commit`, retour sur `main`, `merge`, `branch -d`)


```python
# Écrire ici le script Python et les commandes Git dans l'ordre :
................................................................................
```



<br/>

# 2. FICHIERS CSV (.csv)

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
...

```


➤ Votre script python et vos Commandes Git à effectuer :** (`branch`, `checkout`, `add`, `commit`, retour sur `main`, `merge`, `branch -d`)


```python
# Écrire ici le script Python et les commandes Git dans l'ordre :
................................................................................
```



<br/>

### 2.2 Lecture brute du CSV (texte brut)

**Branche Git à créer :** `csv-brut`

**Emplacement :**  
- Script : `scripts/lecture_brute.py`

- Lisez et affichez simplement le contenu du fichier CSV comme texte brut avec `open()`.



➤ Votre script python et vos Commandes Git à effectuer :** (`branch`, `checkout`, `add`, `commit`, retour sur `main`, `merge`, `branch -d`)


```python
# Écrire ici le script Python et les commandes Git dans l'ordre :
................................................................................
```


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


➤ Votre script python et vos Commandes Git à effectuer :** (`branch`, `checkout`, `add`, `commit`, retour sur `main`, `merge`, `branch -d`)


```python
# Écrire ici le script Python et les commandes Git dans l'ordre :
................................................................................
```



<br/>

### 2.4 Conflit Git volontaire à créer

- Branche `ajout-etudiant-1` (créée depuis `main`)  
  Ajoutez `David,95` dans `notes.csv` puis committez.

- Branche `ajout-etudiant-2` (créée depuis `main`)  
  Ajoutez `Emma,91` dans `notes.csv` puis committez.

- Fusionnez ces deux branches dans `main` pour provoquer un conflit.  
  Résolvez le conflit manuellement et expliquez votre résolution dans `analyse.txt`.

**Commandes Git à effectuer :** `branch`, `checkout`, `add`, `commit`, `checkout main`, `merge`, résoudre conflit, `branch -d`



➤ Votre réponse


```python
# Écrire ici le script Python et les commandes Git dans l'ordre :
................................................................................
```


<br/>

# 3. FICHIERS JSON (.json)

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


➤ Vos Commandes Git à effectuer :


```python
# Écrire ici le script Python et les commandes Git dans l'ordre :
................................................................................
```



<br/>

### 3.2 Conflit Git volontaire JSON à créer

- Branche `json-promo` (depuis main) : Ajoutez `"promo": true` à `"Clé USB"`. Committez.  
- Branche `json-prix` (depuis main) : Changez `"prix"` de `"Clé USB"` à `10.0`. Committez.

- Fusionnez ces deux branches dans `main`.  
- Résolvez le conflit manuellement en conservant les deux changements.  
- Documentez clairement votre résolution dans `analyse.txt`.


<br/>

# 4. FICHIERS NUMPY (.csv avec numpy)

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



➤ Votre script python et vos Commandes Git à effectuer :** (`branch`, `checkout`, `add`, `commit`, retour sur `main`, `merge`, `branch -d`)


```python
# Écrire ici le script Python et les commandes Git dans l'ordre :
................................................................................
```



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


D'accord. Voici la version concise du livrable à remettre :

---

## RAPPORT À REMETTRE

Remettez **un seul fichier** nommé :

```
tp_fichiers_NOM_PRENOM.docx  (ou .pdf, .txt ou .py)
```

Le rapport doit contenir :

- Le **code Python complet** pour chaque étape (copié dans le document)  
- Les **commandes Git** associées à chaque script (branch, checkout, add, commit, merge, branch -d)  
- Les **résolutions de conflits Git**, avec explication claire  
- Les **réponses aux questions finales**  
- Le **résultat complet de** :  
  ```
  git log --oneline --graph
  ```  

Aucun `.zip` ou dossier séparé n’est accepté. Le code et les commandes doivent être intégrés dans ce seul fichier.


**Vérifiez soigneusement chaque étape avant remise du TP.**
