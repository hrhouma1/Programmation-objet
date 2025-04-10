# **Lecture et écriture de fichiers**

## **Objectifs pédagogiques**
À la fin de cette leçon, vous saurez :
- Ouvrir et lire un fichier texte ligne par ligne ou dans son intégralité.
- Écrire dans un fichier, soit en écrasant le contenu, soit en ajoutant.
- Manipuler les fichiers de manière sécurisée à l’aide du mot-clé `with`.
- Gérer les erreurs courantes lors de la manipulation de fichiers.

---

## **1. Ouverture d’un fichier : la fonction `open()`**

La fonction intégrée `open()` permet d’ouvrir un fichier. Sa syntaxe de base est :

```python
f = open('chemin/vers/fichier.txt', 'mode')
```

**Modes les plus courants :**
- `'r'` : lecture (lecture seule, erreur si le fichier n’existe pas)
- `'w'` : écriture (écrase le fichier s’il existe, le crée sinon)
- `'a'` : ajout (écrit à la fin du fichier)
- `'b'` : mode binaire (ex. : `'rb'`, `'wb'`)
- `'r+'` : lecture et écriture

---

## **2. Lire un fichier**

### a) Lire tout le contenu d’un coup

```python
with open('monfichier.txt', 'r') as f:
    contenu = f.read()
    print(contenu)
```

### b) Lire ligne par ligne

```python
with open('monfichier.txt', 'r') as f:
    for ligne in f:
        print(ligne.strip())  # .strip() pour enlever le retour à la ligne
```

### c) Lire toutes les lignes dans une liste

```python
with open('monfichier.txt', 'r') as f:
    lignes = f.readlines()
    print(lignes)
```

---

## **3. Écrire dans un fichier**

### a) Écriture simple (écrase le contenu existant)

```python
with open('sortie.txt', 'w') as f:
    f.write("Ceci est une première ligne.\n")
    f.write("Ceci est une seconde ligne.")
```

### b) Ajout à la fin du fichier

```python
with open('sortie.txt', 'a') as f:
    f.write("\nLigne supplémentaire ajoutée.")
```

---

## **4. Bonnes pratiques : Utiliser le mot-clé `with`**

Le mot-clé `with` gère automatiquement l’ouverture et la fermeture du fichier, même en cas d’erreur. Il est **fortement recommandé** :

```python
with open('fichier.txt', 'r') as f:
    contenu = f.read()
```

Sans `with`, il faut fermer manuellement :

```python
f = open('fichier.txt', 'r')
contenu = f.read()
f.close()
```

---

## **5. Gestion des erreurs : try / except**

Il est utile de capturer les erreurs potentielles, comme un fichier inexistant :

```python
try:
    with open('fichier_inexistant.txt', 'r') as f:
        print(f.read())
except FileNotFoundError:
    print("Erreur : le fichier n'existe pas.")
```

---

## **6. Fichiers binaires (exemple rapide)**

```python
with open('image.png', 'rb') as f:
    data = f.read()
```

---

## **7. Exemple complet**

```python
nom_fichier = 'donnees.txt'

# Écrire des données dans le fichier
with open(nom_fichier, 'w') as f:
    f.write("Nom: Alice\n")
    f.write("Age: 30\n")

# Lire le fichier ligne par ligne
with open(nom_fichier, 'r') as f:
    for ligne in f:
        print("Contenu:", ligne.strip())
```

---

## **8. Exercice pour s'entraîner**

1. Créez un fichier `journal.txt` et ajoutez-y trois lignes de votre choix.
2. Relisez le fichier ligne par ligne et affichez chaque ligne avec son numéro (1, 2, 3).
3. Ajoutez une nouvelle ligne à la fin sans supprimer les lignes précédentes.

