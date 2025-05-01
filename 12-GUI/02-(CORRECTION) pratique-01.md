
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

















## Exercice 4 – Mise en page simple avec plusieurs Labels

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x200")
root.title("Exercice 4")

label_nom = tk.Label(root, text="Nom :")
label_nom.pack()
entry_nom = tk.Entry(root)
entry_nom.pack()

label_prenom = tk.Label(root, text="Prénom :")
label_prenom.pack()
entry_prenom = tk.Entry(root)
entry_prenom.pack()

label_age = tk.Label(root, text="Âge :")
label_age.pack()
entry_age = tk.Entry(root)
entry_age.pack()

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Trois paires étiquette (`Label`) et champ de saisie (`Entry`) pour le nom, le prénom et l’âge.
2. Chaque paire est empilée verticalement avec la méthode `.pack()`.
3. L’interface présente une structure simple de formulaire.

### Énoncé de l’exercice :

Créer une interface contenant trois champs d’information : Nom, Prénom et Âge.  
Chaque champ doit comporter une étiquette descriptive et une zone de saisie juste en dessous.

---

## Exercice 5 – Boutons Radio (Radiobutton)

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x180")
root.title("Exercice 5")

genre = tk.IntVar()

def afficher_genre():
    choix = genre.get()
    if choix == 1:
        print("Genre sélectionné : Homme")
    elif choix == 2:
        print("Genre sélectionné : Femme")
    elif choix == 3:
        print("Genre sélectionné : Autre")
    else:
        print("Aucun choix sélectionné")

radio1 = tk.Radiobutton(root, text="Homme", variable=genre, value=1)
radio2 = tk.Radiobutton(root, text="Femme", variable=genre, value=2)
radio3 = tk.Radiobutton(root, text="Autre", variable=genre, value=3)

radio1.pack()
radio2.pack()
radio3.pack()

btn_valider = tk.Button(root, text="Valider", command=afficher_genre)
btn_valider.pack(pady=10)

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Une variable `IntVar` pour stocker le choix sélectionné parmi les boutons radio.
2. Trois boutons radio (`Radiobutton`) représentant les options : Homme, Femme, Autre.
3. Une fonction `afficher_genre()` pour interpréter la valeur choisie et l’afficher dans la console.
4. Un bouton "Valider" déclenchant l’affichage du choix.

### Énoncé de l’exercice :

Créer une interface avec trois boutons radio permettant de choisir un genre parmi : Homme, Femme ou Autre.  
Lorsqu’on clique sur "Valider", afficher en console le choix sélectionné.

---

## Exercice 6 – Cases à cocher (Checkbutton)

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x200")
root.title("Exercice 6")

python_var = tk.IntVar()
js_var = tk.IntVar()
cpp_var = tk.IntVar()

def afficher_langages():
    print("Langages sélectionnés :")
    if python_var.get():
        print("- Python")
    if js_var.get():
        print("- JavaScript")
    if cpp_var.get():
        print("- C++")

check1 = tk.Checkbutton(root, text="Python", variable=python_var)
check2 = tk.Checkbutton(root, text="JavaScript", variable=js_var)
check3 = tk.Checkbutton(root, text="C++", variable=cpp_var)

check1.pack()
check2.pack()
check3.pack()

btn_afficher = tk.Button(root, text="Afficher", command=afficher_langages)
btn_afficher.pack(pady=10)

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Trois variables `IntVar` associées à chaque case à cocher.
2. Trois composants `Checkbutton` représentant des langages de programmation.
3. Une fonction `afficher_langages()` qui vérifie quelles cases sont cochées et les affiche dans la console.
4. Un bouton "Afficher" qui appelle cette fonction.

### Énoncé de l’exercice :

Créer une interface avec trois cases à cocher représentant les langages suivants : Python, JavaScript, C++.  
Lorsqu’on clique sur le bouton "Afficher", les langages sélectionnés doivent être affichés dans la console.


