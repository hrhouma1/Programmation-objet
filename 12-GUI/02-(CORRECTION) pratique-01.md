
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








## Exercice 7 – Liste déroulante (Listbox)

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x200")
root.title("Exercice 7")

def afficher_selection():
    print("Éléments sélectionnés :")
    for i in listbox.curselection():
        print("-", listbox.get(i))

listbox = tk.Listbox(root, selectmode="multiple")
listbox.insert(1, "Pomme")
listbox.insert(2, "Banane")
listbox.insert(3, "Cerise")
listbox.insert(4, "Orange")
listbox.pack()

btn = tk.Button(root, text="Afficher sélection", command=afficher_selection)
btn.pack(pady=10)

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Une `Listbox` avec le paramètre `selectmode="multiple"` pour permettre plusieurs sélections.
2. Une insertion de plusieurs éléments dans la liste avec la méthode `.insert(index, valeur)`.
3. Une fonction `afficher_selection()` qui récupère les indices sélectionnés avec `.curselection()` et les affiche.
4. Un bouton pour exécuter cette fonction lors du clic.

### Énoncé de l’exercice :

Créer une interface contenant une liste déroulante permettant de sélectionner plusieurs fruits parmi : Pomme, Banane, Cerise, Orange.  
Ajouter un bouton "Afficher sélection" qui affiche en console les fruits sélectionnés.

---

## Exercice 8 – Menu déroulant (OptionMenu)

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x150")
root.title("Exercice 8")

def couleur_choisie(couleur):
    label_resultat.config(text="Vous avez choisi : " + couleur)

couleurs = ["Rouge", "Vert", "Bleu"]
var_couleur = tk.StringVar(value="Choisissez une couleur")

menu = tk.OptionMenu(root, var_couleur, *couleurs, command=couleur_choisie)
menu.pack(pady=10)

label_resultat = tk.Label(root, text="")
label_resultat.pack()

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Une variable `StringVar` initialisée avec un message par défaut.
2. Un menu déroulant `OptionMenu` contenant trois couleurs, lié à cette variable.
3. Une fonction `couleur_choisie()` appelée automatiquement lors de la sélection, qui met à jour un `Label`.
4. Un `Label` dynamique qui affiche la couleur choisie.

### Énoncé de l’exercice :

Créer une interface avec un menu déroulant contenant les couleurs suivantes : Rouge, Vert, Bleu.  
Lorsqu’une couleur est sélectionnée, un message affiché dans un `Label` sous le menu doit indiquer la couleur choisie.



## Exercice 9 – Mise en page améliorée (grid)

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x150")
root.title("Exercice 9")

label_nom = tk.Label(root, text="Nom :")
label_nom.grid(row=0, column=0, sticky="e")
entry_nom = tk.Entry(root)
entry_nom.grid(row=0, column=1)

label_prenom = tk.Label(root, text="Prénom :")
label_prenom.grid(row=1, column=0, sticky="e")
entry_prenom = tk.Entry(root)
entry_prenom.grid(row=1, column=1)

label_age = tk.Label(root, text="Âge :")
label_age.grid(row=2, column=0, sticky="e")
entry_age = tk.Entry(root)
entry_age.grid(row=2, column=1)

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Utilisation de la méthode `.grid(row=, column=)` pour positionner les éléments en tableau.
2. Les étiquettes sont placées dans la colonne 0 et alignées à droite avec `sticky="e"`.
3. Les zones de saisie (`Entry`) sont alignées dans la colonne 1.
4. La disposition est plus structurée et propre qu’avec `.pack()`.

### Énoncé de l’exercice :

Créer une interface avec trois champs : Nom, Prénom et Âge.  
Utiliser la méthode `.grid()` pour positionner les étiquettes à gauche et les champs de saisie à droite, sur trois lignes distinctes.







## Exercice 10 – Interaction clavier

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x100")
root.title("Exercice 10")

def afficher_touche(event):
    print("Touche appuyée :", event.keysym)

root.bind("<KeyPress>", afficher_touche)

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Une fonction `afficher_touche()` prenant un événement clavier en argument et affichant la touche appuyée.
2. Une liaison d’événement via `root.bind("<KeyPress>", afficher_touche)` pour détecter toute pression de touche.
3. Une fenêtre simple qui réagit aux événements clavier même sans composant visible.

### Énoncé de l’exercice :

Créer une fenêtre Tkinter qui affiche dans la console la touche du clavier pressée par l’utilisateur.  
Utiliser l’événement `<KeyPress>` pour détecter les touches.


## Exercice 11 – Interaction souris

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x150")
root.title("Exercice 11")

def afficher_position(event):
    print("Position de la souris :", event.x, event.y)

root.bind("<Motion>", afficher_position)

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Une fonction `afficher_position()` qui récupère les coordonnées de la souris via `event.x` et `event.y`.
2. Un binding avec l’événement `<Motion>` qui déclenche la fonction dès qu’on bouge la souris dans la fenêtre.
3. Affichage des coordonnées actuelles de la souris dans la console.

### Énoncé de l’exercice :

Créer une interface qui affiche en temps réel, dans la console, la position de la souris lorsqu’elle se déplace dans la fenêtre.  
Utiliser l’événement `<Motion>` pour capter les mouvements.



## Exercice 12 – Mini-projet 1 : Formulaire Complet

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("350x300")
root.title("Exercice 12")

# Variables
genre = tk.StringVar()
python_var = tk.IntVar()
java_var = tk.IntVar()
js_var = tk.IntVar()

# Fonction d’affichage
def envoyer():
    print("Nom :", entry_nom.get())
    print("Prénom :", entry_prenom.get())
    print("Genre :", genre.get())
    print("Langages connus :")
    if python_var.get(): print("- Python")
    if java_var.get(): print("- Java")
    if js_var.get(): print("- JavaScript")

# Nom et prénom
tk.Label(root, text="Nom :").grid(row=0, column=0, sticky="e")
entry_nom = tk.Entry(root)
entry_nom.grid(row=0, column=1)

tk.Label(root, text="Prénom :").grid(row=1, column=0, sticky="e")
entry_prenom = tk.Entry(root)
entry_prenom.grid(row=1, column=1)

# Genre
tk.Label(root, text="Genre :").grid(row=2, column=0, sticky="e")
tk.Radiobutton(root, text="Homme", variable=genre, value="Homme").grid(row=2, column=1, sticky="w")
tk.Radiobutton(root, text="Femme", variable=genre, value="Femme").grid(row=3, column=1, sticky="w")
tk.Radiobutton(root, text="Autre", variable=genre, value="Autre").grid(row=4, column=1, sticky="w")

# Langages
tk.Label(root, text="Langages :").grid(row=5, column=0, sticky="ne")
tk.Checkbutton(root, text="Python", variable=python_var).grid(row=5, column=1, sticky="w")
tk.Checkbutton(root, text="Java", variable=java_var).grid(row=6, column=1, sticky="w")
tk.Checkbutton(root, text="JavaScript", variable=js_var).grid(row=7, column=1, sticky="w")

# Bouton
tk.Button(root, text="Envoyer", command=envoyer).grid(row=8, column=1, pady=10)

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Deux `Entry` pour la saisie du nom et du prénom.
2. Trois boutons radio (`Radiobutton`) pour le genre, liés à une variable `StringVar`.
3. Trois cases à cocher (`Checkbutton`) pour les langages de programmation.
4. Une fonction `envoyer()` qui affiche toutes les informations en console.
5. Positionnement des éléments avec `.grid()` pour une mise en page propre.

### Énoncé de l’exercice :

Créer une interface qui permet à un utilisateur de remplir un formulaire complet :
- Deux zones de saisie pour le nom et le prénom
- Trois boutons radio pour le genre : Homme, Femme, Autre
- Trois cases à cocher pour les langages connus : Python, Java, JavaScript  
Un bouton "Envoyer" doit afficher en console toutes les informations saisies.








## Exercice 13 – Mini-projet 2 : Saisie et calcul simple

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x200")
root.title("Exercice 13")

def additionner():
    try:
        a = int(entry1.get())
        b = int(entry2.get())
        resultat.config(text="Résultat : " + str(a + b))
    except ValueError:
        resultat.config(text="Veuillez entrer deux entiers valides.")

tk.Label(root, text="Entier 1 :").pack()
entry1 = tk.Entry(root)
entry1.pack()

tk.Label(root, text="Entier 2 :").pack()
entry2 = tk.Entry(root)
entry2.pack()

tk.Button(root, text="Additionner", command=additionner).pack(pady=10)

resultat = tk.Label(root, text="")
resultat.pack()

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Deux champs `Entry` pour entrer des nombres entiers.
2. Une fonction `additionner()` qui lit, convertit, additionne et affiche le résultat.
3. Une gestion d’erreur avec `try/except` pour éviter les plantages si l’utilisateur entre du texte.
4. Un `Label` dynamique qui affiche le résultat sous le bouton.

### Énoncé de l’exercice :

Créer une interface contenant deux zones de saisie pour des entiers.  
Un bouton "Additionner" calcule la somme des deux entiers et affiche le résultat sous le bouton.  
Le programme doit gérer les cas d’erreur si l’utilisateur entre autre chose qu’un entier.

---

## Exercice 14 – Mini-projet 3 : Jeu de couleur

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("300x150")
root.title("Exercice 14")

def changer_couleur(couleur):
    root.config(bg=couleur)
    label_info.config(text="Couleur actuelle : " + couleur)

couleurs = ["lightblue", "lightgreen", "pink", "yellow"]
var_couleur = tk.StringVar(value="Choisissez une couleur")

menu = tk.OptionMenu(root, var_couleur, *couleurs, command=changer_couleur)
menu.pack(pady=10)

label_info = tk.Label(root, text="")
label_info.pack()

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Une `OptionMenu` avec des couleurs personnalisées (valeurs utilisables par `bg`).
2. Une fonction `changer_couleur()` qui applique la couleur au fond de la fenêtre avec `root.config(bg=...)`.
3. Un `Label` qui indique la couleur actuellement sélectionnée.
4. Une liaison directe entre le menu et la fonction via `command=...`.

### Énoncé de l’exercice :

Créer une interface avec un menu déroulant contenant plusieurs couleurs (par exemple : lightblue, lightgreen, pink, yellow).  
Lorsqu’une couleur est sélectionnée, la couleur de fond de la fenêtre doit changer.  
Afficher sous le menu un message indiquant la couleur actuelle.

---

## Exercice 15 – Projet Final : Interface "Caisse enregistreuse"

### Correction

```python
import tkinter as tk

root = tk.Tk()
root.geometry("350x300")
root.title("Exercice 15")

produits = {
    "Pain": 2.5,
    "Lait": 1.8,
    "Oeufs": 3.2
}

total = 0
panier = []

def ajouter_au_panier():
    global total
    selection = listbox.get(listbox.curselection())
    try:
        quantite = int(entry_quantite.get())
        prix = produits[selection] * quantite
        total += prix
        panier.append(f"{selection} x{quantite} = {prix:.2f} $")
        label_total.config(text=f"Total : {total:.2f} $")
    except:
        label_total.config(text="Erreur : sélection ou quantité invalide.")

def payer():
    print("Contenu du panier :")
    for ligne in panier:
        print(ligne)
    print(f"Total payé : {total:.2f} $")
    label_total.config(text="Paiement effectué.")

# Liste de produits
listbox = tk.Listbox(root)
for produit in produits:
    listbox.insert(tk.END, produit)
listbox.pack()

# Quantité
entry_quantite = tk.Entry(root)
entry_quantite.pack()

tk.Button(root, text="Ajouter au panier", command=ajouter_au_panier).pack(pady=5)
tk.Button(root, text="Payer", command=payer).pack(pady=5)

label_total = tk.Label(root, text="Total : 0.00 $")
label_total.pack()

root.mainloop()
```

### Ce qu’on a ajouté dans cet exercice :

1. Une `Listbox` contenant les produits disponibles.
2. Un `Entry` pour saisir la quantité désirée.
3. Un dictionnaire `produits` contenant le prix de chaque article.
4. Une fonction `ajouter_au_panier()` qui calcule le prix et met à jour le total.
5. Une fonction `payer()` qui affiche le détail des achats dans la console.
6. Une gestion des erreurs pour éviter les crashs si aucun produit ou une mauvaise quantité est sélectionné(e).
7. Un `Label` dynamique qui affiche le total en temps réel.

### Énoncé de l’exercice :

Créer une interface de caisse enregistreuse avec les fonctionnalités suivantes :
- Une `Listbox` contenant les produits : Pain, Lait, Oeufs
- Une zone de saisie pour la quantité
- Un bouton "Ajouter au panier" qui cumule le prix total
- Un bouton "Payer" qui affiche le contenu du panier et le montant total payé
- Un `Label` qui indique en temps réel le total à payer

