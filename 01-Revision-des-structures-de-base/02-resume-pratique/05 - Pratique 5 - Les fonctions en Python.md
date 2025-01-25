# Pratique 5 : Les fonctions en Python

## Table des matières

1. [Objectif](#objectif)  
2. [Note préalable](#note-préalable)  
3. [Préparation](#préparation)  
4. [Exercices](#exercices)  
   - [Exercice 1 : Définir une fonction simple](#exercice-1--définir-une-fonction-simple)  
   - [Exercice 2 : Fonction avec paramètres et retour](#exercice-2--fonction-avec-paramètres-et-retour)  
   - [Exercice 3 : Valeurs par défaut pour les paramètres](#exercice-3--valeurs-par-défaut-pour-les-paramètres)  
   - [Exercice 4 : Retourner plusieurs valeurs](#exercice-4--retourner-plusieurs-valeurs)  
   - [Exercice 5 : Arguments variables avec `*args`](#exercice-5--arguments-variables-avec-args)  
   - [Exercice 6 : Appeler une fonction depuis une autre](#exercice-6--appeler-une-fonction-depuis-une-autre)  
   - [Exercice 7 : Exercice global - Informations dynamiques](#exercice-7--exercice-global---informations-dynamiques)  
5. [Annexe : Exécution rapide avec `python -c`](#annexe--exécution-rapide-avec-python--c)

---

## Objectif
Pratiquer la définition, l'appel, et l'utilisation avancée des fonctions en Python, en testant des concepts dans des fichiers Python ou via `python -c`.

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
   python -m venv pratique5
   pratique5\Scripts\activate
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

### Exercice 1 : Définir une fonction simple
Ajoutez ce code dans `exercice1.py` :
```python
def saluer():
    print("Bonjour !")

saluer()
```

---

### Exercice 2 : Fonction avec paramètres et retour
Ajoutez ce code dans `exercice2.py` :
```python
def additionner(a, b):
    return a + b

print(additionner(5, 7))  # Affiche 12
```

---

### Exercice 3 : Valeurs par défaut pour les paramètres
Ajoutez ce code dans `exercice3.py` :
```python
def saluer(nom="ami"):
    print(f"Bonjour, {nom} !")

saluer()  # Affiche "Bonjour, ami !"
saluer("Alice")  # Affiche "Bonjour, Alice !"
```

---

### Exercice 4 : Retourner plusieurs valeurs
Ajoutez ce code dans `exercice4.py` :
```python
def calculer(valeur):
    carre = valeur ** 2
    cube = valeur ** 3
    return carre, cube

carre, cube = calculer(3)
print(f"Carré : {carre}, Cube : {cube}")  # Affiche "Carré : 9, Cube : 27"
```

---

### Exercice 5 : Arguments variables avec `*args`
Ajoutez ce code dans `exercice5.py` :
```python
def additionner_tout(*nombres):
    return sum(nombres)

print(additionner_tout(1, 2, 3))  # Affiche 6
print(additionner_tout(5, 10))  # Affiche 15
```

---

### Exercice 6 : Appeler une fonction depuis une autre
Ajoutez ce code dans `exercice6.py` :
```python
def chauffer_eau(temperature):
    return f"Eau chauffée à {temperature}°C"

def faire_du_the():
    eau = chauffer_eau(100)
    print(f"Préparer le thé avec {eau}.")

faire_du_the()
```

---

### Exercice 7 : Exercice global - Informations dynamiques
Ajoutez ce code dans `exercice7.py` :
```python
def afficher_infos(**infos):
    for cle, valeur in infos.items():
        print(f"{cle} : {valeur}")

afficher_infos(nom="Marie", age=28, ville="Paris")
```

---

## Annexe : Exécution rapide avec `python -c`

### Méthode
Pour tester rapidement des concepts, utilisez `python -c`.

### Exemples

- **Exercice 1 : Fonction simple**  
  ```bash
  python -c "def saluer(): print('Bonjour !'); saluer()"
  ```

- **Exercice 2 : Fonction avec paramètres et retour**  
  ```bash
  python -c "def additionner(a, b): return a + b; print(additionner(5, 7))"
  ```

- **Exercice 3 : Valeurs par défaut pour les paramètres**  
  ```bash
  python -c "def saluer(nom='ami'): print(f'Bonjour, {nom} !'); saluer(); saluer('Alice')"
  ```

- **Exercice 4 : Retourner plusieurs valeurs**  
  ```bash
  python -c "def calculer(valeur): return valeur**2, valeur**3; carre, cube = calculer(3); print(f'Carré : {carre}, Cube : {cube}')"
  ```

- **Exercice 5 : Arguments variables avec `*args`**  
  ```bash
  python -c "def additionner_tout(*nombres): return sum(nombres); print(additionner_tout(1, 2, 3)); print(additionner_tout(5, 10))"
  ```

- **Exercice 6 : Appeler une fonction depuis une autre**  
  ```bash
  python -c "def chauffer_eau(temperature): return f'Eau chauffée à {temperature}°C'; def faire_du_the(): eau = chauffer_eau(100); print(f'Préparer le thé avec {eau}.'); faire_du_the()"
  ```

- **Exercice 7 : Informations dynamiques**  
  ```bash
  python -c "def afficher_infos(**infos): [print(f'{cle} : {valeur}') for cle, valeur in infos.items()]; afficher_infos(nom='Marie', age=28, ville='Paris')"
  ```

---

### Résumé
- **Pour des exercices détaillés**, utilisez des fichiers Python comme `exercice1.py`, `exercice2.py`, etc.
- **Pour tester rapidement des concepts**, privilégiez la commande `python -c`.
