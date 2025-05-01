
# ⚙ **Préparation de l’environnement sous Windows**

Avant de commencer, crée un environnement virtuel pour isoler le projet :

```bash
# Ouvre l'invite de commandes Windows (cmd) ou PowerShell
# 1. Crée un dossier pour ton projet
mkdir tkinter_projets
cd tkinter_projets

# 2. Crée un environnement virtuel
python -m venv venv

# 3. Active l’environnement virtuel
venv\Scripts\activate

# 4. Tu peux maintenant créer tes fichiers .py dans ce dossier
# (Tkinter est déjà inclus avec Python, pas besoin d'installation)
```






## Exercice 1 – Affichage simple (Label)




















### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x100")
root.title("Exercice 1")

label = tk.Label(root, text="Bienvenue dans Tkinter !", font=("Arial", 16))
label.pack()

root.mainloop()
```

### Ce qu'on a ajouté dans cet exercice :

1. Une fenêtre dimensionnée avec `root.geometry("300x100")`.
2. Une étiquette (`Label`) contenant le texte "Bienvenue dans Tkinter !", en police Arial taille 16.
3. Un positionnement automatique de l’étiquette avec `.pack()`.

### Énoncé de l’exercice :

Créer une interface graphique simple qui affiche une étiquette avec le texte "Bienvenue dans Tkinter !".  
La fenêtre doit avoir une taille de 300x100 pixels et utiliser une police Arial de taille 16.

---

## Exercice 2 – Ajouter un bouton pour quitter

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x100")
root.title("Exercice 2")

label = tk.Label(root, text="Bienvenue dans Tkinter !", font=("Arial", 16))
label.pack()

btn_quitter = tk.Button(root, text="Quitter", command=root.destroy, bg="red", fg="white")
btn_quitter.pack(pady=10)

root.mainloop()
```

### Ce qu'on a ajouté dans cet exercice :

1. Un bouton `Button` affichant "Quitter".
2. Une action `command=root.destroy` liée à ce bouton pour fermer la fenêtre.
3. Une mise en forme du bouton : fond rouge (`bg="red"`) et texte blanc (`fg="white"`).
4. Un espacement vertical entre les éléments avec `pady=10`.

### Énoncé de l’exercice :

À partir de l’exercice précédent, ajouter un bouton "Quitter" sous l’étiquette.  
Ce bouton doit fermer la fenêtre lorsqu’on clique dessus. Il doit être coloré avec un fond rouge et un texte blanc.

---

## Exercice 3 – Champ de saisie (Entry) et affichage

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x120")
root.title("Exercice 3")

def afficher_texte():
    contenu = entry.get()
    print("Vous avez saisi :", contenu)

label = tk.Label(root, text="Entrez votre nom :", font=("Arial", 12))
label.pack()

entry = tk.Entry(root, width=30)
entry.pack()

btn_valider = tk.Button(root, text="Valider", command=afficher_texte, bg="#2E75FF", fg="white")
btn_valider.pack(pady=10)

root.mainloop()
```

### Ce qu'on a ajouté dans cet exercice :

1. Une étiquette demandant à l’utilisateur de saisir son nom.
2. Une zone de saisie `Entry` pour écrire du texte.
3. Une fonction `afficher_texte()` qui lit le contenu de l’entrée et l’affiche dans la console.
4. Un bouton "Valider" déclenchant cette fonction, avec une mise en forme personnalisée.

### Énoncé de l’exercice :

Créer une interface avec une zone de texte dans laquelle l’utilisateur peut saisir son nom.  
Ajouter une étiquette explicative "Entrez votre nom :" au-dessus de cette zone.  
Un bouton "Valider" doit afficher le texte saisi dans la console.
