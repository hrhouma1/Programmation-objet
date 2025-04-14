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


<br/>


## Exercice 1 : Lire un fichier JSON simple

```python
import json

with open("files/eleves.json", encoding="utf-8") as f:
    eleves = json.load(f)

for eleve in eleves:
    print(f"{eleve['prenom']} {eleve['nom']} a eu {eleve['note']}/20")
```


---

## Exercice 2 : Extraire une valeur d’un objet JSON

**Objectif :** Extraire une configuration.

**Instructions :**
1. Charger `config.json`
2. Afficher l’adresse complète du serveur sous forme :  
   `Connexion au serveur 127.0.0.1 sur le port 8080`





<br/>

<br/>


## Exercice 2 : Extraire une valeur d’un objet JSON

```python
import json

with open("files/config.json", encoding="utf-8") as f:
    config = json.load(f)

print(f"Connexion au serveur {config['serveur']} sur le port {config['port']}")
```

<br/>





---

## Exercice 3 : Calculer la moyenne des notes

**Objectif :** Extraire des données numériques et les traiter.

**Instructions :**
1. Charger `eleves.json`
2. Calculer et afficher la moyenne des notes





## Exercice 3 : Calculer la moyenne des notes

```python
import json

with open("files/eleves.json", encoding="utf-8") as f:
    eleves = json.load(f)

notes = [eleve["note"] for eleve in eleves]
moyenne = sum(notes) / len(notes)

print(f"Moyenne des notes : {moyenne:.2f}/20")
```

<br/>




---

## Exercice 4 : Créer un nouveau fichier JSON

**Objectif :** Générer un nouveau fichier à partir de données modifiées.

**Instructions :**
1. Ajouter un champ `"mention"` dans `eleves.json` :
   - `"Très bien"` si note ≥ 16
   - `"Bien"` si note ≥ 14
   - `"Passable"` sinon
2. Écrire un nouveau fichier `eleves_mentions.json`



## Exercice 4 : Créer un nouveau fichier JSON avec mentions

```python
import json

with open("files/eleves.json", encoding="utf-8") as f:
    eleves = json.load(f)

for eleve in eleves:
    note = eleve["note"]
    if note >= 16:
        eleve["mention"] = "Très bien"
    elif note >= 14:
        eleve["mention"] = "Bien"
    else:
        eleve["mention"] = "Passable"

with open("files/eleves_mentions.json", "w", encoding="utf-8") as f:
    json.dump(eleves, f, indent=2, ensure_ascii=False)

print("Fichier eleves_mentions.json généré.")
```

<br/>




---

## Exercice 5 : Trouver les produits en rupture

**Objectif :** Lire un tableau JSON et filtrer les résultats.

**Instructions :**
1. Charger `produits.json`
2. Afficher les produits dont le stock est à 0 sous forme :  
   `Le produit Cahier est en rupture de stock.`




## Exercice 5 : Trouver les produits en rupture

```python
import json

with open("files/produits.json", encoding="utf-8") as f:
    produits = json.load(f)

for produit in produits:
    if produit["stock"] == 0:
        print(f"Le produit {produit['nom']} est en rupture de stock.")
```

<br/>



---

## Exercice 6 : Augmenter les prix de 10 %

**Objectif :** Modifier dynamiquement des données.

**Instructions :**
1. Charger `produits.json`
2. Augmenter le prix de chaque produit de 10 %
3. Sauvegarder les nouveaux prix dans `produits_maj.json`




## Exercice 6 : Augmenter les prix de 10 %

```python
import json

with open("files/produits.json", encoding="utf-8") as f:
    produits = json.load(f)

for produit in produits:
    produit["prix"] = round(produit["prix"] * 1.10, 2)

with open("files/produits_maj.json", "w", encoding="utf-8") as f:
    json.dump(produits, f, indent=2, ensure_ascii=False)

print("Fichier produits_maj.json généré.")
```

<br/>




---

## Exercice 7 : Créer un dictionnaire dynamique et l’exporter

**Objectif :** Générer une structure JSON à partir de Python.

**Instructions :**
1. Demander à l’utilisateur de saisir 3 contacts (nom, téléphone, email)
2. Stocker les données dans une liste de dictionnaires
3. Sauvegarder le tout dans `contacts.json`


## Exercice 7 : Créer un dictionnaire dynamique et l’exporter

```python
import json

contacts = []

for i in range(3):
    nom = input(f"Nom du contact {i+1} : ")
    tel = input("Téléphone : ")
    email = input("Email : ")
    contacts.append({"nom": nom, "telephone": tel, "email": email})

with open("files/contacts.json", "w", encoding="utf-8") as f:
    json.dump(contacts, f, indent=2, ensure_ascii=False)

print("Fichier contacts.json généré.")
```

<br/>




---

## Exercice 8 : Fusionner plusieurs fichiers JSON

**Objectif :** Lire deux fichiers et combiner leur contenu.

**Instructions :**
1. Créer un fichier `eleves_bis.json` avec 2 nouveaux élèves
2. Lire `eleves.json` et `eleves_bis.json`
3. Combiner les deux listes en une seule
4. Enregistrer dans `eleves_combines.json`




## Exercice 8 : Fusionner deux fichiers JSON

```python
import json

with open("files/eleves.json", encoding="utf-8") as f1:
    liste1 = json.load(f1)

with open("files/eleves_bis.json", encoding="utf-8") as f2:
    liste2 = json.load(f2)

fusion = liste1 + liste2

with open("files/eleves_combines.json", "w", encoding="utf-8") as f:
    json.dump(fusion, f, indent=2, ensure_ascii=False)

print("Fichier eleves_combines.json généré.")
```
