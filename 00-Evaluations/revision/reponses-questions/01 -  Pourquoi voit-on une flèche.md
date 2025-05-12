

# Pourquoi voit-on une flèche `->` dans les définitions de fonctions Python ?

## 1. Introduction

En Python, vous pouvez voir parfois une flèche `->` après le nom d’une fonction, y compris dans des méthodes comme `__str__`. Cette flèche **ne fait pas partie de la syntaxe de base** obligatoire de Python, mais elle est utilisée pour **indiquer le type de retour attendu** d’une fonction. On appelle cela une **annotation de type**.

---

## 2. Syntaxe de base

### Sans annotation de type :

```python
def __str__(self):
    return f"Nom : {self.nom}"
```

### Avec annotation de type :

```python
def __str__(self) -> str:
    return f"Nom : {self.nom}"
```

> Ici, `-> str` signifie que la méthode retourne une valeur de type `str` (chaîne de caractères).

---

## 3. À quoi sert l’annotation `->` ?

* Elle **n’est pas obligatoire**.
* Elle sert à **mieux documenter le code**.
* Elle **n’est pas vérifiée automatiquement** par Python, mais peut être utilisée par des outils comme `mypy` ou des IDE pour vous avertir en cas d’erreur.

---

## 4. Exemple complet

```python
class Film:
    def __init__(self, titre, realisateur):
        self.titre = titre
        self.realisateur = realisateur

    def __str__(self) -> str:
        return f"Titre : {self.titre} | Réalisateur : {self.realisateur}"
```

### Utilisation :

```python
f = Film("Inception", "Christopher Nolan")
print(f)
```

### Sortie :

```
Titre : Inception | Réalisateur : Christopher Nolan
```

---

## 5. Différence avec `lambda`

Un autre symbole fréquent est `lambda`, une fonction anonyme définie en une seule ligne. Exemple :

```python
double = lambda x: x * 2
```

Ce `:` n’a rien à voir avec `->` : c’est une autre syntaxe qui n’indique pas de type.

---

## 6. Résumé

| Élément          | Signification                         |
| ---------------- | ------------------------------------- |
| `-> str`         | Type de retour attendu : `str`        |
| Optionnel        | Oui                                   |
| Vérifié ?        | Non, sauf si vous utilisez des outils |
| Bonnes pratiques | Recommandé dans du code professionnel |


