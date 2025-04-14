# TP : Manipulation de fichiers JSON avec Python

**Durée estimée** : 1h à 1h30  
**Niveau** : Débutant à intermédiaire  
**Fichiers requis** : `eleves.json`, `config.json`, `produits.json`, `eleves_bis.json`  
**Objectifs** :
- Lire et écrire des fichiers JSON
- Extraire, modifier et enregistrer des données
- Maîtriser les structures Python associées (liste, dictionnaire)
- Appliquer des conditions et des boucles sur des données JSON



# Partie 1 : Lecture de fichiers JSON

### Exercice 1.1 : Lecture simple  
Lisez le fichier `eleves.json` et affichez pour chaque élève la phrase :  
`<Prénom> <Nom> a eu <Note>/20`

### Exercice 1.2 : Configuration  
Lisez le fichier `config.json` et affichez le message :  
`Connexion au serveur <serveur> sur le port <port>`


# Partie 2 : Traitements de données

### Exercice 2.1 : Moyenne des élèves  
Calculez et affichez la moyenne des notes du fichier `eleves.json`.  
Affichez le résultat avec **deux décimales**.

### Exercice 2.2 : Ajouter une mention  
Ajoutez à chaque élève un champ `"mention"` selon la note :
- ≥ 16 : `"Très bien"`
- ≥ 14 : `"Bien"`
- sinon : `"Passable"`  
Sauvegardez le nouveau fichier sous le nom `eleves_mentions.json`.



# Partie 3 : Gestion d’inventaire

### Exercice 3.1 : Produits en rupture  
Lisez `produits.json` et affichez les noms des produits avec stock nul sous la forme :  
`Le produit <nom> est en rupture de stock.`

### Exercice 3.2 : Mise à jour des prix  
Augmentez les prix de tous les produits de 10 %.  
Écrivez les données modifiées dans un fichier `produits_maj.json`.



# Partie 4 : Interaction utilisateur

### Exercice 4.1 : Saisie de contacts  
Créez un script qui demande à l’utilisateur de saisir 3 contacts (nom, téléphone, email)  
Stockez les résultats dans une liste de dictionnaires et sauvegardez dans `contacts.json`.



# Partie 5 : Fusion de fichiers

### Exercice 5.1 : Fusion d’élèves  
Fusionnez les listes du fichier `eleves.json` et de `eleves_bis.json`.  
Sauvegardez le tout dans `eleves_combines.json`.
