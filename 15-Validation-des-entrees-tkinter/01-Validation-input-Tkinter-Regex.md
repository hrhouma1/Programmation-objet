# **Validation des entrées avec Tkinter et expressions régulières**



# **1. Préparer l’environnement de travail**

Avant tout projet en Python, il est conseillé de créer un environnement virtuel pour isoler les bibliothèques utilisées.

### Étapes (Windows, Terminal ou Anaconda Prompt) :

```bash
mkdir projet_tkinter_validation
cd projet_tkinter_validation
python -m venv env
env\Scripts\activate
pip install tk
```

> Cela permet de travailler dans un espace propre, sans interférer avec d'autres projets Python sur votre machine.



# **2. Exemple complet 1 – Champ texte limité à 10 caractères**

### Code complet

```python
import tkinter as tk

def valider_longueur(texte):
    return len(texte) <= 10

root = tk.Tk()
root.title("Validation de longueur")
champ = tk.Entry(root,
                 validate="key",
                 validatecommand=(root.register(valider_longueur), "%P"))
champ.pack(padx=10, pady=10)
root.mainloop()
```

> Ce programme crée une interface graphique avec un seul champ.
> L’utilisateur ne peut taper que 10 caractères maximum.
> `%P` transmet le contenu **proposé** du champ.
> `validate="key"` déclenche la validation **à chaque frappe**.



# **3. Exemple complet 2 – Validation alphabétique avec message d’erreur**

### Objectif : Accepter uniquement des lettres (majuscules ou minuscules) et afficher une alerte sinon.

### Code :

```python
import tkinter as tk
import re

def verifier_lettres(texte):
    return bool(re.fullmatch(r"[A-Za-z]*", texte))

def message_erreur():
    message.set("Veuillez saisir uniquement des lettres.")

root = tk.Tk()
root.title("Entrée lettres uniquement")

message = tk.StringVar()
champ = tk.Entry(root,
                 validate="key",
                 validatecommand=(root.register(verifier_lettres), "%P"),
                 invalidcommand=(root.register(message_erreur),))
champ.pack()

label = tk.Label(root, textvariable=message, fg="red")
label.pack()

root.mainloop()
```

> `re.fullmatch(...)` vérifie que **toute la chaîne** correspond au motif.
> Le champ refuse les chiffres ou symboles.
> `invalidcommand` déclenche `message_erreur()` si la validation échoue.
> Le message s’affiche dynamiquement sous le champ.



# **4. Exemple complet 3 – Nom d’utilisateur entre 3 et 12 caractères, lettres seulement**

### Code :

```python
import tkinter as tk
import re

def valider_utilisateur(texte):
    return bool(re.fullmatch(r"[A-Za-z]{3,12}", texte))

def erreur_utilisateur():
    info.set("3 à 12 lettres uniquement.")

root = tk.Tk()
root.title("Nom d'utilisateur")

info = tk.StringVar()
champ = tk.Entry(root,
                 validate="key",
                 validatecommand=(root.register(valider_utilisateur), "%P"),
                 invalidcommand=(root.register(erreur_utilisateur),))
champ.pack()

msg = tk.Label(root, textvariable=info, fg="blue")
msg.pack()

root.mainloop()
```

> Ce champ n’autorise que les lettres, entre 3 et 12 caractères.
> Le motif `[A-Za-z]{3,12}` permet cette contrainte.
> Le message s’actualise si la règle est violée.



# **5. Exemple complet 4 – Âge numérique entre 0 et 120**

### Code :

```python
import tkinter as tk

def valider_age(texte):
    if texte == "":
        return True
    if texte.isdigit():
        return 0 <= int(texte) <= 120
    return False

root = tk.Tk()
root.title("Âge (0-120)")

champ = tk.Entry(root,
                 validate="key",
                 validatecommand=(root.register(valider_age), "%P"))
champ.pack()

root.mainloop()
```

> Ici, `.isdigit()` est utilisé pour vérifier si l’entrée est **entière**.
> La conversion avec `int()` permet de vérifier si l’âge est dans une **plage raisonnable**.
> La chaîne vide est autorisée pour effacer.



# **6. Exemple complet 5 – Numéro de téléphone (514-XXX-XXXX)**

### Code :

```python
import tkinter as tk
import re

def valider_tel(texte):
    return bool(re.fullmatch(r"514-\d{3}-\d{4}", texte))

root = tk.Tk()
root.title("Numéro téléphone format 514-XXX-XXXX")

champ = tk.Entry(root,
                 validate="key",
                 validatecommand=(root.register(valider_tel), "%P"))
champ.pack()

root.mainloop()
```

> Ce champ accepte uniquement les numéros au format exact `514-123-4567`.
> `\d{3}` et `\d{4}` signifient respectivement **trois chiffres** et **quatre chiffres**.
> Le motif doit être saisi intégralement pour réussir la validation.



# **7. Exercices simples (avec corrections après)**

### **Exercice 1 :** Créez un champ qui accepte uniquement les codes postaux canadiens (ex. `H1A 1B2`).

### **Exercice 2 :** Créez un champ qui valide un mot de passe avec au moins 1 majuscule, 1 chiffre, et une longueur minimale de 6 caractères.

### **Exercice 3 :** Validez un champ qui accepte des noms de fichiers se terminant en `.pdf` ou `.docx`.



# **Corrigés attendus**

> **Exercice 1 – Code postal canadien**
> `^[A-Za-z]\d[A-Za-z] \d[A-Za-z]\d$`
> Trois blocs : lettre/chiffre/lettre - espace - chiffre/lettre/chiffre

> **Exercice 2 – Mot de passe sécurisé**
> `^(?=.*[A-Z])(?=.*\d).{6,}$`
> Contient au moins une majuscule, un chiffre, et au moins 6 caractères

> **Exercice 3 – Nom de fichier**
> `^\w+\.(pdf|docx)$`
> Accepte des noms comme "rapport.pdf", "memoire.docx"

