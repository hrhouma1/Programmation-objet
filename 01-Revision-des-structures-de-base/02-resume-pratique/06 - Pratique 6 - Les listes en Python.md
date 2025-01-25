# Pratique 6 : Les listes en Python

## Table des matières

1. [Objectif](#objectif)  
2. [Note préalable](#note-préalable)  
3. [Préparation](#préparation)  
4. [Exercices](#exercices)  
   - [Exercice 1 : Créer une liste](#exercice-1--créer-une-liste)  
   - [Exercice 2 : Accéder aux éléments d’une liste](#exercice-2--accéder-aux-éléments-dune-liste)  
   - [Exercice 3 : Modifier une liste](#exercice-3--modifier-une-liste)  
   - [Exercice 4 : Concaténation et répétition de listes](#exercice-4--concaténation-et-répétition-de-listes)  
   - [Exercice 5 : Parcourir une liste](#exercice-5--parcourir-une-liste)  
   - [Exercice 6 : Slicing et inversion](#exercice-6--slicing-et-inversion)  
   - [Exercice 7 : Méthodes utiles pour les listes](#exercice-7--méthodes-utiles-pour-les-listes)  
5. [Annexe : Exécution rapide avec `python -c`](#annexe--exécution-rapide-avec-python--c)

---

## Objectif
Explorer les fonctionnalités des listes en Python, y compris leur création, manipulation, et les méthodes associées.

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
   python -m venv pratique6
   pratique6\Scripts\activate
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

---

## Exercices

### Exercice 1 : Créer une liste
Ajoutez ce code dans `exercice1.py` :
```python
ma_liste = [42, "Python", 3.14, False]
print(ma_liste)
```

---

### Exercice 2 : Accéder aux éléments d’une liste
Ajoutez ce code dans `exercice2.py` :
```python
animaux = ["chien", "chat", "lapin"]
print(animaux[0])  # Premier élément
print(animaux[-1])  # Dernier élément
```

---

### Exercice 3 : Modifier une liste
Ajoutez ce code dans `exercice3.py` :
```python
fruits = ["pomme", "orange"]
fruits.append("banane")
fruits.extend(["kiwi", "mangue"])
print(fruits)
```

---

### Exercice 4 : Concaténation et répétition de listes
Ajoutez ce code dans `exercice4.py` :
```python
liste1 = [1, 2]
liste2 = [3, 4]
resultat = liste1 + liste2
repetition = liste1 * 3
print(resultat)
print(repetition)
```

---

### Exercice 5 : Parcourir une liste
Ajoutez ce code dans `exercice5.py` :
```python
couleurs = ["rouge", "vert", "bleu"]
for couleur in couleurs:
    print(couleur)
```

---

### Exercice 6 : Slicing et inversion
Ajoutez ce code dans `exercice6.py` :
```python
nombres = [0, 1, 2, 3, 4, 5]
print(nombres[1:4])  # Sous-liste
print(nombres[::-1])  # Liste inversée
```

---

### Exercice 7 : Méthodes utiles pour les listes
Ajoutez ce code dans `exercice7.py` :
```python
nombres = [3, 1, 4, 1, 5]
print(nombres.count(1))  # Compte les 1
print(nombres.index(4))  # Position de 4
nombres.sort()
print(nombres)  # Trié
nombres.reverse()
print(nombres)  # Ordre inversé
```

---

## Annexe : Exécution rapide avec `python -c`

### Méthode
Pour tester rapidement des expressions ou des concepts, utilisez `python -c`.

### Exemples

- **Exercice 1 : Créer une liste**  
  ```bash
  python -c "ma_liste = [42, 'Python', 3.14, False]; print(ma_liste)"
  ```

- **Exercice 2 : Accéder aux éléments d’une liste**  
  ```bash
  python -c "animaux = ['chien', 'chat', 'lapin']; print(animaux[0]); print(animaux[-1])"
  ```

- **Exercice 3 : Modifier une liste**  
  ```bash
  python -c "fruits = ['pomme', 'orange']; fruits.append('banane'); fruits.extend(['kiwi', 'mangue']); print(fruits)"
  ```

- **Exercice 4 : Concaténation et répétition de listes**  
  ```bash
  python -c "liste1 = [1, 2]; liste2 = [3, 4]; print(liste1 + liste2); print(liste1 * 3)"
  ```

- **Exercice 5 : Parcourir une liste**  
  ```bash
  python -c "couleurs = ['rouge', 'vert', 'bleu']; [print(couleur) for couleur in couleurs]"
  ```

- **Exercice 6 : Slicing et inversion**  
  ```bash
  python -c "nombres = [0, 1, 2, 3, 4, 5]; print(nombres[1:4]); print(nombres[::-1])"
  ```

- **Exercice 7 : Méthodes utiles pour les listes**  
  ```bash
  python -c "nombres = [3, 1, 4, 1, 5]; print(nombres.count(1)); print(nombres.index(4)); nombres.sort(); print(nombres); nombres.reverse(); print(nombres)"
  ```

---

### Résumé
- **Pour des exercices détaillés**, utilisez des fichiers Python comme `exercice1.py`, `exercice2.py`, etc.
- **Pour tester rapidement des concepts**, privilégiez la commande `python -c`.
