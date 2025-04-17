##  TRAVAIL PRATIQUE – MANIPULATION DE FICHIERS ET GESTION AVEC GIT  
**Nom de l'étudiant :** Jean Dupont  
**Groupe :** 401-1A



# 1.1 INITIALISATION DU PROJET

#### ➤ **Vos commandes Git :**
```bash
# Étape 1 : Créer un dossier de travail
mkdir tp_fichiers_git
cd tp_fichiers_git

# Étape 2 : Initialiser le dépôt Git
git init

# Étape 3 : Créer les répertoires pour les scripts et les données
mkdir scripts
mkdir data

# Étape 4 : Créer un fichier README
echo "# TP FICHIERS ET GIT" > README.md

# Étape 5 : Ajouter et valider le fichier README
git add README.md
git commit -m "Initialisation du projet avec README.md"

# Étape 6 : Enregistrer dans le log de commandes
echo "git init" > git_commands.txt
echo "git add README.md" >> git_commands.txt
echo "git commit -m \"Initialisation du projet avec README.md\"" >> git_commands.txt
```



# 1.2 Écriture sans utiliser with open()

#### ➤ **Script Python à créer :** `scripts/ecriture_sans_with.py`

```python
# scripts/ecriture_sans_with.py

fichier = open("data/journal.txt", "w", encoding="utf-8")

fichier.write("Jour 1 : Introduction\n")
fichier.write("Jour 2 : Variables\n")
fichier.write("Jour 3 : Conditions\n")
fichier.write("Jour 4 : Boucles\n")
fichier.write("Jour 5 : Fonctions\n")
fichier.write("Jour 6 : Listes\n")
fichier.write("Jour 7 : Dictionnaires\n")
fichier.write("Jour 8 : Tuples\n")
fichier.write("Jour 9 : Ensembles\n")
fichier.write("Jour 10 : Manipulation de fichiers texte\n")
fichier.write("Jour 11 : Manipulation de fichiers CSV\n")
fichier.write("Jour 12 : Manipulation de fichiers JSON\n")
fichier.write("Jour 13 : NumPy - Sauvegarde de tableaux\n")
fichier.write("Jour 14 : NumPy - Chargement de tableaux\n")
fichier.write("Jour 15 : Graphiques avec matplotlib\n")
fichier.write("Jour 16 : Résolution d'erreurs JSON\n")
fichier.write("Jour 17 : Gestion des exceptions en Python\n")
fichier.write("Jour 18 : Écriture avancée avec format()\n")
fichier.write("Jour 19 : Encodage de fichiers texte\n")
fichier.write("Jour 20 : Conclusion et révision\n")

fichier.close()
```



# Étape intermédiaire : Exécution et vérification

#### ➤ **Exécuter le script :**
```bash
python scripts/ecriture_sans_with.py
```

#### ➤ **Vérifier le contenu généré :**
```bash
cat data/journal.txt
```

#### ➤ **Contenu attendu dans journal.txt :**
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



# Commandes Git à effectuer :

```bash
# Étape 1 : Créer et basculer sur une nouvelle branche
git branch txt-sans-with
git checkout txt-sans-with

# Étape 2 : Ajouter le script Python et le fichier de données
git add scripts/ecriture_sans_with.py
git add data/journal.txt

# Étape 3 : Commit clair et descriptif
git commit -m "Ajout script sans with open() + génération de journal.txt"

# Étape 4 : Revenir sur main
git checkout main

# Étape 5 : Fusionner la branche txt-sans-with
git merge txt-sans-with

# Étape 6 : Supprimer la branche
git branch -d txt-sans-with
```



# `git_commands.txt` mis à jour :

```txt
git init
git add README.md
git commit -m "Initialisation du projet avec README.md"

# Partie 1.2
git branch txt-sans-with
git checkout txt-sans-with
python scripts/ecriture_sans_with.py
cat data/journal.txt
git add scripts/ecriture_sans_with.py
git add data/journal.txt
git commit -m "Ajout script sans with open() + génération de journal.txt"
git checkout main
git merge txt-sans-with
git branch -d txt-sans-with
```
