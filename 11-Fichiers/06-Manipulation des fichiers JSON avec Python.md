# Manipulation des fichiers JSON avec Python

---

## 1. Qu’est-ce qu’un fichier JSON ?

### Définition
**JSON** signifie **JavaScript Object Notation**. C’est un format de données **texte** permettant de représenter des **données structurées** sous forme de paires **clé/valeur**.

Il est très utilisé pour :
- les échanges entre applications web
- les API
- le stockage de configurations

---

### Exemple de fichier JSON (`eleves.json`)
```json
[
  {
    "nom": "Martin",
    "prenom": "Julie",
    "note": 15
  },
  {
    "nom": "Durand",
    "prenom": "Paul",
    "note": 12
  }
]
```

---

## 2. Lecture d’un fichier JSON en Python

### Étape par étape
```python
import json

# Ouverture et lecture du fichier JSON
with open("files/eleves.json", "r", encoding="utf-8") as f:
    donnees = json.load(f)

# Affichage
for eleve in donnees:
    print(f"{eleve['prenom']} {eleve['nom']} a eu {eleve['note']}/20")
```

### Résultat :
```
Julie Martin a eu 15/20
Paul Durand a eu 12/20
```

---

## 3. Structure des données chargées

Le contenu est converti en :
- une **liste** Python (si le fichier commence par `[`)
- contenant des **dictionnaires** (si chaque objet est un `{}`)

---

## 4. Écriture dans un fichier JSON

### Exemple

```python
import json

# Données à enregistrer
donnees = [
    {"nom": "Doe", "prenom": "John", "note": 17},
    {"nom": "Smith", "prenom": "Jane", "note": 18}
]

# Écriture dans un fichier JSON
with open("files/nouveau.json", "w", encoding="utf-8") as f:
    json.dump(donnees, f, indent=2, ensure_ascii=False)
```

### Explication :
- `indent=2` : formatte avec une indentation de 2 espaces
- `ensure_ascii=False` : permet d’afficher les accents

---

## 5. Lire un objet JSON simple (non liste)

### Exemple (`config.json`)
```json
{
  "serveur": "localhost",
  "port": 8080,
  "debug": true
}
```

```python
import json

with open("files/config.json", "r", encoding="utf-8") as f:
    config = json.load(f)

print(config["serveur"])
print(config["port"])
```

---

## 6. Comparaison JSON vs CSV

| Critère          | CSV                         | JSON                           |
|------------------|-----------------------------|--------------------------------|
| Format            | Tabulaire (colonnes)        | Hiérarchique / structuré       |
| Facile à lire     | Oui                         | Moyennement (selon structure) |
| Encodage          | Texte brut                  | Texte structuré                |
| Utilisation typique| Tableurs, données simples   | API, configs, objets imbriqués |

---

## 7. Quiz (vrai/faux)

1. Un fichier JSON peut contenir une liste d’objets.  
2. La méthode `json.load()` permet d’écrire un fichier JSON.  
3. Les clés dans un JSON doivent être entre guillemets.  
4. Un JSON peut contenir un booléen (`true`, `false`).  
5. `json.dump()` permet de lire un fichier JSON.

---

## 8. Correction

| Question | Réponse |
|----------|---------|
| 1        | Vrai    |
| 2        | Faux    |
| 3        | Vrai    |
| 4        | Vrai    |
| 5        | Faux    |

---

## 9. Erreurs fréquentes

| Erreur | Cause fréquente | Solution |
|--------|------------------|----------|
| `JSONDecodeError` | Fichier mal formaté | Vérifier les virgules, crochets, guillemets |
| Clé introuvable | Clé absente dans le dictionnaire | Utiliser `get()` ou tester l'existence |
| Encodage incorrect | Caractères spéciaux mal affichés | Ajouter `encoding="utf-8"` et `ensure_ascii=False` |
