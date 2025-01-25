# Pratique 4 : Les chaînes de caractères en Python

## Table des matières

1. [Objectif](#objectif)  
2. [Note préalable](#note-préalable)  
3. [Préparation](#préparation)  
4. [Exercices](#exercices)  
   - [Exercice 1 : Concaténation de chaînes](#exercice-1--concaténation-de-chaînes)  
   - [Exercice 2 : Interpolation de chaînes](#exercice-2--interpolation-de-chaînes)  
   - [Exercice 3 : Indexation et extraction de sous-chaînes](#exercice-3--indexation-et-extraction-de-sous-chaînes)  
   - [Exercice 4 : Méthodes de transformation](#exercice-4--méthodes-de-transformation)  
   - [Exercice 5 : Recherche et remplacement](#exercice-5--recherche-et-remplacement)  
   - [Exercice 6 : Découpage et assemblage](#exercice-6--découpage-et-assemblage)  
   - [Exercice 7 : Exercice global - Transformation et analyse](#exercice-7--exercice-global---transformation-et-analyse)  
5. [Annexe : Exécution rapide avec `python -c`](#annexe--exécution-rapide-avec-python--c)

---

## Objectif
Pratiquer la manipulation des chaînes en Python en écrivant du code dans des fichiers Python ou en testant rapidement des concepts via `python -c`.

---

## Note préalable
Le module `venv` est inclus par défaut dans Python 3.3 et versions ultérieures.  
- **Si `venv` n'est pas disponible**, installez-le avec :
  ```bash
  pip install venv
  ```
- **Pour plusieurs versions de Python installées**, utilisez des commandes spécifiques comme `python3.11`.

---

## Préparation

1. **Créer un environnement virtuel** :  
   ```bash
   python -m venv pratique4
   pratique4\Scripts\activate
   ```

2. **Créer plusieurs fichiers Python** :  
   ```cmd
   notepad exercice1.py   # Fichier pour l'exercice 1
   notepad exercice2.py   # Fichier pour l'exercice 2
   notepad exercice3.py   # Fichier pour l'exercice 3
   notepad exercice4.py   # Fichier pour l'exercice 4
   notepad exercice5.py   # Fichier pour l'exercice 5
   notepad exercice6.py   # Fichier pour l'exercice 6
   notepad exercice7.py   # Fichier pour l'exercice 7
   ```

3. **Exécutez chaque fichier après y avoir ajouté le code correspondant dans la section ci-bas** :
   ```bash
   python exemple1.py
   python exemple2.py
   python exemple3.py
   python exemple4.py
   python exemple5.py
   python exemple6.py
   ```


---

## Exercices

### Exercice 1 : Concaténation de chaînes
Ajoutez ce code dans `exercice1.py` :
```python
prenom = "Alice"
nom = "Martin"
nom_complet = prenom + " " + nom
print(nom_complet)
```

---

### Exercice 2 : Interpolation de chaînes
Ajoutez ce code dans `exercice2.py` :
```python
ville = "Paris"
message = f"Bienvenue à {ville} !"
print(message)
```

---

### Exercice 3 : Indexation et extraction de sous-chaînes
Ajoutez ce code dans `exercice3.py` :
```python
texte = "Python"
print(texte[0])  # Premier caractère
print(texte[-1])  # Dernier caractère
print(texte[0:3])  # Sous-chaîne
```

---

### Exercice 4 : Méthodes de transformation
Ajoutez ce code dans `exercice4.py` :
```python
texte = " Bonjour "
print(texte.upper())  # Majuscules
print(texte.lower())  # Minuscules
print(texte.strip())  # Suppression d'espaces
```

---

### Exercice 5 : Recherche et remplacement
Ajoutez ce code dans `exercice5.py` :
```python
texte = "Apprendre Python est amusant."
print(texte.find("Python"))  # Trouver 'Python'
print(texte.replace("Python", "la programmation"))  # Remplacer
```

---

### Exercice 6 : Découpage et assemblage
Ajoutez ce code dans `exercice6.py` :
```python
phrase = "Python est génial"
mots = phrase.split(" ")  # Découper
print(mots)
nouvelle_phrase = " ".join(mots)  # Assembler
print(nouvelle_phrase)
```

---

### Exercice 7 : Exercice global - Transformation et analyse
Ajoutez ce code dans `exercice7.py` :
```python
phrase = "La programmation en Python est passionnante."
print(phrase.upper())  # Majuscules
print(len(phrase.split()))  # Compte les mots
print(phrase.replace("Python", "JavaScript"))  # Remplacer Python par JavaScript
```

---

## Annexe : Exécution rapide avec `python -c`

### Méthode
Pour tester rapidement des expressions ou des concepts, utilisez `python -c`.

### Exemples

- **Exercice 1 : Concaténation de chaînes**  
  ```bash
  python -c "prenom = 'Alice'; nom = 'Martin'; print(prenom + ' ' + nom)"
  ```

- **Exercice 2 : Interpolation de chaînes**  
  ```bash
  python -c "ville = 'Paris'; print(f'Bienvenue à {ville} !')"
  ```

- **Exercice 3 : Indexation et extraction de sous-chaînes**  
  ```bash
  python -c "texte = 'Python'; print(texte[0]); print(texte[-1]); print(texte[0:3])"
  ```

- **Exercice 4 : Méthodes de transformation**  
  ```bash
  python -c "texte = ' Bonjour '; print(texte.upper()); print(texte.lower()); print(texte.strip())"
  ```

- **Exercice 5 : Recherche et remplacement**  
  ```bash
  python -c "texte = 'Apprendre Python est amusant.'; print(texte.find('Python')); print(texte.replace('Python', 'la programmation'))"
  ```

- **Exercice 6 : Découpage et assemblage**  
  ```bash
  python -c "phrase = 'Python est génial'; mots = phrase.split(' '); print(mots); print(' '.join(mots))"
  ```

- **Exercice 7 : Transformation et analyse**  
  ```bash
  python -c "phrase = 'La programmation en Python est passionnante.'; print(phrase.upper()); print(len(phrase.split())); print(phrase.replace('Python', 'JavaScript'))"
  ```

---

### Résumé
- **Pour des exercices détaillés**, utilisez des fichiers Python comme `exercice1.py`, `exercice2.py`, etc.
- **Pour tester rapidement des concepts**, privilégiez la commande `python -c`.
