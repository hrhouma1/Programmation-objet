# Cours : **Programmation Orientée Objet avec Tkinter (Interface Graphique en Python)**

---

## 1. Introduction à Tkinter

**Tkinter** est une bibliothèque graphique intégrée à Python, permettant de créer des interfaces utilisateurs (GUI).

---

## 2. L’objet Tk

Pour démarrer avec Tkinter, il faut créer une fenêtre principale, appelée **objet racine** (`root`).

```python
import tkinter as tk

# Création de l'élément racine
root = tk.Tk()

# Affichage de la fenêtre
root.mainloop()

print("Ce code sera exécuté à la fermeture de la fenêtre Tkinter")
```

---

## 3. Redimensionnement et Titre de la Fenêtre

### a) Définir une taille pour la fenêtre
```python
import tkinter as tk
root = tk.Tk()
root.geometry("200x100")
root.mainloop()
```

### b) Définir un titre pour la fenêtre
```python
import tkinter as tk
root = tk.Tk()
root.title("Mon premier programme")
root.mainloop()
```

---

## 4. Exemple complet : Affichage d’une étiquette et d’un bouton

```python
import tkinter as tk

# Création de la fenêtre racine
root = tk.Tk()
root.geometry("500x500")
root.title('Fenêtre')

# Création d'une étiquette
texte1 = tk.Label(root, text='Bonjour tout le monde !', fg='red')
texte1.pack()

# Création d'un bouton
bouton1 = tk.Button(root, text='Quitter', command=root.destroy)
bouton1.pack()

# Affichage de la fenêtre
root.mainloop()
```

---

## 5. Composants Tkinter : Définition et Ajout

Un **composant** (ou **widget**) est un élément d’interface, comme un bouton, une étiquette, une zone de texte.

Exemple :
```python
import tkinter as tk

root = tk.Tk()

# Bouton
btn = tk.Button(root, text="Récupérer sélection", bg="#2E75FF", fg="white")
btn.pack()

root.mainloop()
```

---

## 6. Paramètres communs des composants

- `text` : texte affiché
- `bg` : couleur de fond
- `fg` : couleur du texte
- `font` : police et taille du texte

Exemple :
```python
import tkinter as tk

root = tk.Tk()
btn = tk.Button(root, text="Récupérer sélection", bg="#2E75FF", fg="white")
btn.pack()

root.mainloop()
```

---

## 7. Composant Label (Étiquette)

```python
import tkinter as tk

root = tk.Tk()

texte1 = tk.Label(root, text="Hello World!", fg="red", bg="black", font=("Arial", 16))
texte1.pack()

root.mainloop()
```

---

## 8. Composant Button (Bouton)

### a) Bouton avec fonction de rappel
```python
import tkinter as tk

root = tk.Tk()

def clic():
    print("Tu m'as cliqué!")

btn = tk.Button(root, text="Clic-moi!", command=clic, bg="#2E75FF", fg="white")
btn.pack()

root.mainloop()
```

### b) Bouton pour fermer la fenêtre
```python
import tkinter as tk

root = tk.Tk()

btn_quit = tk.Button(root, text="Quitter", command=root.destroy, bg="red", fg="white")
btn_quit.pack()

root.mainloop()
```

---

## 9. Composant Entry (Saisie utilisateur)

```python
import tkinter as tk

root = tk.Tk()
root.title("Entry")
root.geometry("200x40")

saisie = tk.Entry(root, bg="gray", fg="white")
saisie.pack()

root.mainloop()
```

### Entry avec affichage de la saisie :

```python
import tkinter as tk

root = tk.Tk()
root.title("Entry")
root.geometry("200x40")

def afficher_saisie():
    print("\n\nVous avez entré :", saisie.get(), '\n\n')

label = tk.Label(root, text="Entrez votre nom :")
label.pack()

saisie = tk.Entry(root, bg="gray", fg="white")
saisie.pack()

btn = tk.Button(root, text="Valider", command=afficher_saisie, bg="#2E75FF", fg="white")
btn.pack()

root.mainloop()
```

---

## 10. Composant Radiobutton (Bouton radio)

```python
import tkinter as tk

root = tk.Tk()
root.title("Radio")
root.geometry("200x100")

var = tk.IntVar()

radio_btn_1 = tk.Radiobutton(root, variable=var, text="Choix 1", value=1)
radio_btn_2 = tk.Radiobutton(root, variable=var, text="Choix 2", value=2)
radio_btn_3 = tk.Radiobutton(root, variable=var, text="Choix 3", value=3)

radio_btn_1.pack()
radio_btn_2.pack()
radio_btn_3.pack()

root.mainloop()
```

---

## 11. Composant Checkbutton (Case à cocher)

```python
import tkinter as tk

root = tk.Tk()
root.title("Checkbutton")
root.geometry("200x100")

check_btn_1 = tk.Checkbutton(root, text="Choix 1", onvalue=1, offvalue=0)
check_btn_2 = tk.Checkbutton(root, text="Choix 2", onvalue=1, offvalue=0)
check_btn_3 = tk.Checkbutton(root, text="Choix 3", onvalue=1, offvalue=0)

check_btn_1.pack()
check_btn_2.pack()
check_btn_3.pack()

root.mainloop()
```

---

## 12. Composant Listbox (Liste déroulante)

```python
import tkinter as tk

root = tk.Tk()
root.title("Listbox")
root.geometry("200x100")

listbox = tk.Listbox(root, selectmode="multiple")
listbox.insert(1, "JavaScript")
listbox.insert(2, "Python")
listbox.insert(3, "Java")
listbox.insert(4, "Rust")

listbox.pack()

root.mainloop()
```

Avec sélection multiple :
```python
import tkinter as tk

root = tk.Tk()
root.title("Listbox")
root.geometry("200x100")

def on_select():
    print(listbox.curselection())
    for i in listbox.curselection():
        print(listbox.get(i))

listbox = tk.Listbox(root, selectmode="multiple")
listbox.insert(1, "JavaScript")
listbox.insert(2, "Python")
listbox.insert(3, "Java")
listbox.insert(4, "Rust")
listbox.pack()

btn = tk.Button(root, text="Récupérer sélection", command=on_select, bg="#2E75FF", fg="white")
btn.pack()

root.mainloop()
```

---

## 13. Composant OptionMenu (Menu déroulant)

```python
import tkinter as tk

root = tk.Tk()
root.title("Menu")
root.geometry("200x100")

couleurs = ["Rouge", "Vert", "Bleu"]
couleur_selectionne = tk.StringVar(value="Sélectionnez une couleur")

menu_couleur = tk.OptionMenu(root, couleur_selectionne, *couleurs)
menu_couleur.pack()

root.mainloop()
```

Avec callback sur le choix :
```python
import tkinter as tk

root = tk.Tk()
root.title("Menu")
root.geometry("200x100")

def menu_change(couleur):
    print("Couleur sélectionnée:", couleur)

couleurs = ["Rouge", "Vert", "Bleu"]
couleur_selectionne = tk.StringVar(value="Sélectionnez une couleur")

menu_couleur = tk.OptionMenu(root, couleur_selectionne, command=menu_change, *couleurs)
menu_couleur.pack()

root.mainloop()
```

---

## 14. Variables Tkinter

Tkinter utilise des variables spéciales : `StringVar`, `IntVar`, `DoubleVar`, `BooleanVar`.

Exemples :

```python
import tkinter as tk

my_var = tk.StringVar(value="valeur")
my_int_var = tk.IntVar(value=12)
my_double_var = tk.DoubleVar(value=2.2)
my_bool_var = tk.BooleanVar(value=False)

# Exemple d'utilisation
my_label = tk.Label(root, textvariable=my_var)
```

---

## 15. Changer dynamiquement une variable Tkinter

```python
import tkinter as tk

def update_label():
    label_text.set(entry.get())

root = tk.Tk()
root.title("Exemple avec tkinter")

label_text = tk.StringVar()

entry = tk.Entry(root, textvariable=label_text)
entry.pack(pady=10)

label = tk.Label(root, textvariable=label_text)
label.pack()

update_button = tk.Button(root, text="Mettre à jour l'étiquette", command=update_label)
update_button.pack(pady=10)

root.mainloop()
```

---

## 16. Évènements de Clavier et de Souris

### Clavier : Détecter l'appui d’une touche
```python
import tkinter as tk

def fonction_de_rappel(event):
    print("Touche enfoncée :", event.keysym)

root = tk.Tk()
root.bind("<KeyPress>", fonction_de_rappel)

root.mainloop()
```

### Souris : Détecter le mouvement ou le clic
```python
import tkinter as tk

def fonction_de_rappel(event):
    print("Position de la souris :", event.x, event.y)

root = tk.Tk()
root.bind("<Motion>", fonction_de_rappel)

root.mainloop()
```

---

## 17. Conclusion

Avec Tkinter, on peut créer des interfaces riches et interactives en Python grâce :
- Aux **widgets**,
- À la **gestion des évènements**,
- Et aux **variables dynamiques** (`StringVar`, `IntVar`, etc.).

