# **Introduction aux expressions régulières (RegEx) en Python**



# **1. Définition et objectif**

Une **expression régulière** est une notation symbolique utilisée pour spécifier des motifs (patterns) de texte. Ces motifs servent à rechercher, valider, extraire ou transformer des chaînes de caractères dans des documents, formulaires ou bases de données.

> En d’autres termes, une expression régulière est une manière formelle de poser la question :
> *“Est-ce que cette chaîne de caractères correspond exactement à ce que je cherche ?”*



# **2. Pourquoi utiliser des expressions régulières ?**

Elles permettent d’automatiser des tâches courantes :

* Vérifier qu’une adresse email est bien formée
* Repérer des codes postaux, des numéros ou des mots-clés
* Extraire des données précises dans un texte (ex. : prix, dates)
* Supprimer des caractères indésirables (ex. : ponctuation, symboles)



# **3. Utilisation minimale en Python**

```python
import re

texte = "Bienvenue à Université123"
motif = r"[A-Za-z]+[0-9]+"
resultat = re.search(motif, texte)

if resultat:
    print("Motif détecté :", resultat.group())
else:
    print("Aucune correspondance.")
```

> Ce code vérifie s’il existe un mot composé de lettres suivi de chiffres, comme "Université123".



# **4. Caractères littéraux**

Ce sont les lettres, chiffres ou symboles que l’on cherche tels quels.

```python
re.search("Paris", "Paris est une capitale")  # Match
re.search("Berlin", "Capitale : Berlin")      # Match
re.search("Tokyo", "Ville de Kyoto")          # Aucun match
```



# **5. Symboles spéciaux (métacaractères)**

Les expressions régulières utilisent des symboles pour exprimer des motifs complexes :

| Symbole | Description                           | Exemple                        |
| ------- | ------------------------------------- | ------------------------------ |
| `.`     | Tout caractère sauf saut de ligne     | `a.b` → "acb", "a1b"           |
| `^`     | Début de la chaîne                    | `^Nom` → "Nomade", "Nominal"   |
| `$`     | Fin de la chaîne                      | `fin$` → "La fin"              |
| `*`     | Zéro ou plusieurs                     | `ab*` → "a", "ab", "abb", etc. |
| `+`     | Une ou plusieurs                      | `ab+` → "ab", "abb"            |
| `?`     | Zéro ou un                            | `colou?r` → "color", "colour"  |
| `\d`    | Un chiffre (0-9)                      | `\d+` → "2024"                 |
| `\w`    | Lettre, chiffre ou "\_"               | `\w+` → "Variable\_1"          |
| `\s`    | Espace, tabulation, retour à la ligne | `\s+` → " "                    |



# **6. Quantificateurs – Préciser combien de fois**

| Motif    | Signification        |
| -------- | -------------------- |
| `x{3}`   | exactement trois x   |
| `x{2,5}` | entre deux et cinq x |
| `x{4,}`  | au moins quatre x    |

```python
re.search(r"\d{4}", "Année : 1999")   # Match
re.search(r"A{2,3}", "AA")            # Match
re.search(r"A{2,3}", "AAAA")          # Match partiel "AAA"
```



# **7. Groupes et alternatives**

* **Parenthèses `()`** pour grouper
* **Barre verticale `|`** pour exprimer "ou"

```python
re.search(r"(chien|chat)", "J’ai un chien")   # Match
re.search(r"(a|e|i|o|u)", "xyz")              # Aucun match
```


# **8. Fonctions de base en Python**

| Fonction       | Usage                                   |
| -------------- | --------------------------------------- |
| `re.search()`  | Cherche la **première occurrence**      |
| `re.findall()` | Retourne **toutes les correspondances** |
| `re.sub()`     | **Remplace** un motif par autre chose   |
| `re.split()`   | **Découpe** une chaîne selon un motif   |

### Exemple :

```python
texte = "Nom: Alice, Age: 22; Note: 19.5"
valeurs = re.split(r"[:,;] ?", texte)
print(valeurs)
```

> Résultat : `['Nom', 'Alice', 'Age', '22', 'Note', '19.5']`



# **9. Valider un email**

```python
email = "utilisateur@mail.fr"
motif = r"^[\w\.-]+@[\w-]+\.[a-z]{2,4}$"

if re.match(motif, email):
    print("Email valide.")
else:
    print("Email invalide.")
```

### Explication :

* `^[\w\.-]+` : commence par une série de lettres/chiffres/points
* `@` : obligatoire
* `[\w-]+` : nom de domaine
* `\.[a-z]{2,4}$` : extension `.fr`, `.com`, etc.



# **10. Vérification manuelle d’une adresse email**

Méthode sans expression régulière, utile pour comprendre les règles de base :

```python
def verif_email(email):
    if '@' not in email or '.' not in email.split('@')[-1]:
        return False
    return True
```




# **11. Nettoyage d’un nom d’utilisateur**

### Objectif : supprimer chiffres et caractères spéciaux

```python
nom = "Pauline_98!"
nettoye = re.sub(r"[^A-Za-z]", "", nom)
print(nettoye)  # Pauline
```

> On conserve uniquement les lettres. `[^...]` signifie "tout ce qui est inclut après ^".



# **12. Exercices d’entraînement**

### Exercice 1

Validez si la chaîne "Code-XYZ-2023" contient un mot suivi d’un tiret, puis trois majuscules, un autre tiret et quatre chiffres.

> Motif attendu : `\w+-[A-Z]{3}-\d{4}`
> Test : `"Code-XYZ-2023"` → Match



### Exercice 2

Extraire toutes les dates au format `JJ-MM-AAAA` dans un texte :

```python
texte = "Les examens auront lieu le 15-06-2024 et le 03-07-2025."
dates = re.findall(r"\d{2}-\d{2}-\d{4}", texte)
print(dates)
```

> Résultat : `['15-06-2024', '03-07-2025']`



### Exercice 3

Supprimer tous les caractères non alphabétiques d’un nom complet :

```python
nom = "M@r!e-L0u"
nettoye = re.sub(r"[^a-zA-Z]", "", nom)
print(nettoye)
```

> Résultat attendu : `"MreLou"`



### Exercice 4

Valider un mot de passe d’au moins 8 caractères, avec une majuscule, un chiffre et un symbole.

> Motif possible : `^(?=.*[A-Z])(?=.*\d)(?=.*[@#$%^&+=]).{8,}$`
> Test : `"Professeur@2024"` → Valide



## **13. Résumé**

1. Une expression régulière définit un **motif textuel** à reconnaître.
2. Python fournit plusieurs fonctions pour **chercher**, **remplacer**, **valider** ou **découper** des chaînes avec ces motifs.
3. Les **métacaractères** permettent de généraliser les recherches (par exemple, tous les chiffres, toutes les majuscules, etc.).
4. Les **quantificateurs** donnent la possibilité de fixer ou d'encadrer le nombre d’occurrences.
5. Il est crucial de **tester les motifs progressivement**, en commençant par des cas simples.


