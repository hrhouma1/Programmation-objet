# TRAVAIL PRATIQUE – MANIPULATION DE FICHIERS ET GESTION AVEC GIT  
**Nom de l'étudiant :** [ex: Jean Dupont]  
**Groupe :** [ex: 401-1A]



# 1.1 INITIALISATION DU PROJET

#### ➤ **Vos commandes Git :**
```bash
# Créer un dossier pour le projet
mkdir tp_fichiers_git
cd tp_fichiers_git

# Initialiser le dépôt Git
git init

# Créer les dossiers nécessaires
mkdir scripts
mkdir data

# Ajouter un fichier README de base
echo "# TP FICHIERS ET GIT" > README.md

# Ajouter le fichier à l’index Git
git add README.md
git commit -m "Initialisation du projet avec README"

# Enregistrer cette commande dans le fichier de log
echo "git init" >> git_commands.txt
echo "git add README.md" >> git_commands.txt
echo "git commit -m \"Initialisation du projet avec README\"" >> git_commands.txt
```



# 1.2 Écriture sans utiliser with open()

#### ➤ **Script Python (scripts/ecriture_sans_with.py) :**

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


# ➤ **Commandes Git à effectuer :**
```bash
# Créer et se placer sur la branche
git branch txt-sans-with
git checkout txt-sans-with

# Ajouter le script et le fichier de données généré
git add scripts/ecriture_sans_with.py
git add data/journal.txt

# Commit clair
git commit -m "Ajout du script d'écriture sans with open() et génération de journal.txt"

# Revenir sur main
git checkout main

# Fusionner la branche
git merge txt-sans-with

# Supprimer la branche fusionnée
git branch -d txt-sans-with
```



# ➤ **Log dans git_commands.txt (à compléter dans le dépôt) :**
```txt
git branch txt-sans-with
git checkout txt-sans-with
git add scripts/ecriture_sans_with.py
git add data/journal.txt
git commit -m "Ajout du script d'écriture sans with open() et génération de journal.txt"
git checkout main
git merge txt-sans-with
git branch -d txt-sans-with
```

