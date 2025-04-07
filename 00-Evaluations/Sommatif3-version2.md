# **Exercice 1 – Université et départements**

Modélisez le système suivant à l’aide d’un **diagramme de classes UML** :

1. Une **université** comporte plusieurs **départements**.  
2. Chaque **département** possède un **nom**.  
3. L’**université** dispose d’une **adresse**.



# **Exercice 2 – Animaux domestiques**

Modélisez le système suivant à l’aide d’un **diagramme de classes UML** :

1. Un **animal** peut être un **chat** ou un **chien**.  
2. Tous les **animaux** possèdent un **nom**.  
3. Les **chats** peuvent **grimper**, les **chiens** peuvent **aboyer**.



# **Exercice 3 – Ordinateur et composants**

Modélisez le système suivant à l’aide d’un **diagramme de classes UML** :

1. Un **ordinateur** comprend un **processeur**, une **mémoire**, et un **disque dur**.  
2. Chaque **composant** possède un **modèle**.




# **Exercice 4 – LOG GIT (À REPRODUIRE)**


> **“Reproduisez exactement cet historique Git avec toutes les branches, les commits, les suppressions et les fusions dans l’ordre exact.”**



# **Résultat attendu de `git log --oneline --graph --all` :**

```text
*   e12e3cc (main) Fusion de v1 dans main
|\  
| *   c4adf43 Fusion de v2 dans v1
| |\  
| | *   7fd238d Fusion de v3 dans v2
| | |\  
| | | *   a9182f0 Fusion de v4 dans v3
| | | |\  
| | | | *   84d8b67 Fusion de v5 dans v4
| | | | |\  
| | | | | * v5 commit 3 depuis v5
| | | | | * v5 commit 2 depuis v5
| | | | | * v5 commit 1 depuis v5
| | | | * v4 commit 3 depuis v4
| | | | * v4 commit 2 depuis v4
| | | | * v4 commit 1 depuis v4
| | | * v3 commit 3 depuis v3
| | | * v3 commit 2 depuis v3
| | | * v3 commit 1 depuis v3
| | * v2 commit 3 depuis v2
| | * v2 commit 2 depuis v2
| | * v2 commit 1 depuis v2
| * v1 commit 3 depuis v1
| * v1 commit 2 depuis v1
| * v1 commit 1 depuis v1
* 4a01bcd Initial commit sur main
```



# **Énoncé**

## Objectif

Vous devez **reproduire parfaitement** l’historique Git ci-dessus, en créant :

- Une branche principale `main`
- Une **chaîne de 5 branches dépendantes** :
  ```
  v1 → v2 → v3 → v4 → v5
  ```
  Chaque branche est **créée à partir de la précédente**, jamais depuis `main`.

- Chaque branche (`v1` à `v5`) doit contenir **3 commits** avec les messages suivants :
  ```
  vX commit Y depuis vX
  ```
  Exemple : `v3 commit 2 depuis v3`

- Ensuite, vous devez effectuer **des fusions successives inversées** :  
  `v5 → v4`, `v4 → v3`, `v3 → v2`, `v2 → v1`, `v1 → main`, en ajoutant à chaque fois un **commit de fusion explicite (`--no-ff`)**.

- Supprimez chaque branche après sa fusion avec :
  ```bash
  git branch -d vX
  ```



# Commandes finales attendues :

- Utilisez **exactement** :
  - `git init`
  - `git checkout -b`
  - `echo`, `>>`, `touch` pour modifier les fichiers
  - `git add`, `git commit -m`
  - `git merge --no-ff -m "..."`
  - `git branch -d`
  - `git log --oneline --graph --all` pour vérifier



# Livrables à rendre

- Dossier `.git` de `reconstruction-complexe`
- Fichier `git_commands.txt` avec **toutes les commandes utilisées**
- Capture d’écran du `git log --oneline --graph --all`



















<br/>
<br/>


# **Exercice 5 Git – Gestion de conflit et récupération de fichier supprimé**



## Objectifs pédagogiques

- Comprendre la gestion des branches dans un projet Git  
- Gérer un **conflit de fusion** manuellement  
- Savoir **récupérer un fichier supprimé accidentellement** avec Git  
- Maintenir un historique propre et lisible



## Contexte

Vous travaillez dans un dépôt Git collaboratif. Le fichier `rapport.txt` contient des informations essentielles.  
Deux branches (`main` et `amélioration`) ont été modifiées séparément, ce qui génère un **conflit lors de la fusion**.  
Vous devrez ensuite simuler la **suppression accidentelle du fichier**, puis le **récupérer correctement** à l’aide de Git.



## Instructions

> Lisez chaque étape avec rigueur. Suivez précisément chaque instruction.  
> Remplissez les lignes de points de suspension avec les commandes exactes utilisées.  
> Ne modifiez pas les noms de fichiers ou de branches.

---

### Étape 1 – Initialiser le dépôt

1. Créez un dossier `exo-conflit-suppression`  
2. Initialisez un dépôt Git  
3. Créez un fichier `rapport.txt` avec le contenu suivant :  
   ```
   Rapport initial du projet
   ```
4. Ajoutez le fichier et faites un commit avec le message suivant :  
   ```
   Initialisation avec rapport.txt
   ```

> Commandes utilisées :  
```
...
...
...
...
```

---

### Étape 2 – Créer la branche `amelioration`

1. Créez et basculez sur la branche `amélioration`  
2. Ajoutez dans `rapport.txt` la ligne suivante :  
   ```
   Contenu ajouté depuis amélioration
   ```
3. Enregistrez les modifications et effectuez un commit avec le message :  
   ```
   Ajout dans amélioration
   ```

> Commandes utilisées :  
```
...
...
...
```

---

### Étape 3 – Modifier aussi la branche `main`

1. Revenez sur la branche `main`  
2. Ajoutez la ligne suivante dans `rapport.txt` :  
   ```
   Contenu ajouté depuis main
   ```
3. Effectuez un commit avec le message suivant :  
   ```
   Ajout dans main
   ```

> Commandes utilisées :  
```
...
...
...
```

---

### Étape 4 – Fusion et résolution du conflit

1. Depuis `main`, tentez de fusionner la branche `amelioration`  
2. Un conflit apparaît dans `rapport.txt`  
3. Résolvez **manuellement** le conflit en conservant les deux modifications  
4. Une fois corrigé, ajoutez le fichier et validez avec le message suivant :  
   ```
   Résolution manuelle du conflit entre main et amélioration
   ```

> Contenu final attendu dans `rapport.txt` :  
```
...
...
...
```

> Commandes utilisées :  
```
...
...
...
```

---

### Étape 5 – Suppression accidentelle du fichier

1. Supprimez le fichier `rapport.txt`  
2. Informez Git de la suppression  
3. Faites un commit avec le message suivant :  
   ```
   Suppression accidentelle de rapport.txt
   ```

> Commandes utilisées :  
```
...
...
...
```

---

### Étape 6 – Restauration du fichier supprimé

Vous devez maintenant **récupérer** `rapport.txt` dans son état précédent, avant sa suppression.

> Commandes utilisées :  
```
...
...
...
```

---

## Livrables à rendre

- Le dossier `.git` du projet `exo-conflit-suppression`  
- Un fichier `git_commands.txt` contenant **toutes les commandes utilisées dans l’ordre**  
- Une capture d’écran du fichier `rapport.txt` **non résolu** (conflit visible avec `<<<<<<<`)  
- Une **explication textuelle** des étapes de résolution et de restauration

---

## Questions de développement

1. **Qu’est-ce qu’un conflit Git ?**  
   Expliquez en vos mots ce qu’est un conflit dans Git, dans quel contexte il apparaît, et comment il est détecté.

   Réponse :  
   ```
   ...
   ...
   ...
   ```

2. **Comment restaurer un fichier supprimé dans Git ?**  
   Donnez deux méthodes différentes pour récupérer un fichier supprimé accidentellement dans un dépôt Git.

   Réponse :  
   ```
   ...
   ...
   ...
   ```

