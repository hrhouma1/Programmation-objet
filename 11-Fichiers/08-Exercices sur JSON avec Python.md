# Exercices sur JSON avec Python



## 📂 Fichiers à utiliser (à placer dans `files/`)

**Fichier 1 : `eleves.json`**
```json
[
  {"nom": "Durand", "prenom": "Marie", "note": 14},
  {"nom": "Martin", "prenom": "Paul", "note": 18},
  {"nom": "Benoit", "prenom": "Julie", "note": 11}
]
```

**Fichier 2 : `config.json`**
```json
{
  "serveur": "127.0.0.1",
  "port": 8080,
  "debug": true
}
```

**Fichier 3 : `produits.json`**
```json
[
  {"id": 1, "nom": "Stylo", "prix": 2.5, "stock": 100},
  {"id": 2, "nom": "Cahier", "prix": 3.0, "stock": 0},
  {"id": 3, "nom": "Règle", "prix": 1.5, "stock": 25}
]
```

---

## Exercice 1 : Lire un fichier JSON simple

**Objectif :** Afficher la note de chaque élève.

**Instructions :**
1. Charger `eleves.json`
2. Afficher le prénom, nom et la note de chaque élève sous forme :  
   `Marie Durand a eu 14/20`

---

## Exercice 2 : Extraire une valeur d’un objet JSON

**Objectif :** Extraire une configuration.

**Instructions :**
1. Charger `config.json`
2. Afficher l’adresse complète du serveur sous forme :  
   `Connexion au serveur 127.0.0.1 sur le port 8080`

---

## Exercice 3 : Calculer la moyenne des notes

**Objectif :** Extraire des données numériques et les traiter.

**Instructions :**
1. Charger `eleves.json`
2. Calculer et afficher la moyenne des notes

---

## Exercice 4 : Créer un nouveau fichier JSON

**Objectif :** Générer un nouveau fichier à partir de données modifiées.

**Instructions :**
1. Ajouter un champ `"mention"` dans `eleves.json` :
   - `"Très bien"` si note ≥ 16
   - `"Bien"` si note ≥ 14
   - `"Passable"` sinon
2. Écrire un nouveau fichier `eleves_mentions.json`

---

## Exercice 5 : Trouver les produits en rupture

**Objectif :** Lire un tableau JSON et filtrer les résultats.

**Instructions :**
1. Charger `produits.json`
2. Afficher les produits dont le stock est à 0 sous forme :  
   `Le produit Cahier est en rupture de stock.`

---

## Exercice 6 : Augmenter les prix de 10 %

**Objectif :** Modifier dynamiquement des données.

**Instructions :**
1. Charger `produits.json`
2. Augmenter le prix de chaque produit de 10 %
3. Sauvegarder les nouveaux prix dans `produits_maj.json`

---

## Exercice 7 : Créer un dictionnaire dynamique et l’exporter

**Objectif :** Générer une structure JSON à partir de Python.

**Instructions :**
1. Demander à l’utilisateur de saisir 3 contacts (nom, téléphone, email)
2. Stocker les données dans une liste de dictionnaires
3. Sauvegarder le tout dans `contacts.json`

---

## Exercice 8 : Fusionner plusieurs fichiers JSON

**Objectif :** Lire deux fichiers et combiner leur contenu.

**Instructions :**
1. Créer un fichier `eleves_bis.json` avec 2 nouveaux élèves
2. Lire `eleves.json` et `eleves_bis.json`
3. Combiner les deux listes en une seule
4. Enregistrer dans `eleves_combines.json`


