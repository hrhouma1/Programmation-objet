# **Série d'Exercices Progressifs Tkinter**



## **Exercice 1 – Affichage simple (Label)**

**Objectif** : Créer une fenêtre qui affiche une simple étiquette.

- Créer une fenêtre de dimensions `300x100`
- Ajouter une étiquette affichant **"Bienvenue dans Tkinter !"**
- Utiliser une police Arial taille 16

**Instructions** :  
– Utilisez `tk.Label()`  
– Utilisez `.pack()` pour positionner.



## **Exercice 2 – Ajouter un bouton pour quitter**

**Objectif** : Ajouter un bouton qui ferme la fenêtre.

- Reprendre l'exercice 1
- Ajouter un bouton "Quitter"
- Quand on clique dessus, la fenêtre doit se fermer.

**Instructions** :  
– Utilisez `command=root.destroy` pour le bouton.



## **Exercice 3 – Champ de saisie (Entry) et affichage**

**Objectif** : Lire une entrée utilisateur et l'afficher dans la console.

- Créer une zone de saisie (`Entry`)
- Ajouter un bouton "Valider"
- Lorsque l'utilisateur clique, afficher le texte saisi dans la console.

**Instructions** :  
– Utilisez `.get()` sur l'Entry.



## **Exercice 4 – Mise en page simple avec plusieurs Labels**

**Objectif** : Afficher plusieurs informations.

- Ajouter trois labels l'un en dessous de l'autre :
  - "Nom :"
  - "Prénom :"
  - "Âge :"
- Ajouter trois zones `Entry` correspondantes.



## **Exercice 5 – Boutons Radio (Radiobutton)**

**Objectif** : Choisir une option unique.

- Ajouter trois boutons radio pour choisir :
  - "Homme"
  - "Femme"
  - "Autre"
- Afficher la sélection dans la console après validation.

**Instructions** :  
– Utilisez `tk.IntVar()` pour stocker la sélection.



## **Exercice 6 – Cases à cocher (Checkbutton)**

**Objectif** : Choisir plusieurs options.

- Ajouter trois cases à cocher :
  - "Python"
  - "JavaScript"
  - "C++"
- Lorsque l'on clique sur "Afficher", afficher la liste des langages cochés.



## **Exercice 7 – Liste déroulante (Listbox)**

**Objectif** : Sélection multiple dans une liste.

- Créer une `Listbox` avec les éléments suivants :
  - "Pomme"
  - "Banane"
  - "Cerise"
  - "Orange"
- Ajouter un bouton "Afficher sélection" qui affiche les éléments choisis.



## **Exercice 8 – Menu déroulant (OptionMenu)**

**Objectif** : Menu de sélection.

- Créer un menu déroulant avec :
  - "Rouge"
  - "Vert"
  - "Bleu"
- Afficher la couleur choisie dans un `Label` sous le menu.



## **Exercice 9 – Mise en page améliorée (Grid)**

**Objectif** : Apprendre `grid()` pour un placement précis.

- Reprendre l'exercice 4.
- Placer chaque Label et chaque Entry avec `.grid(row=, column=)`.



## **Exercice 10 – Interaction clavier**

**Objectif** : Réagir à une touche du clavier.

- Afficher dans la console la touche appuyée par l'utilisateur.



## **Exercice 11 – Interaction souris**

**Objectif** : Réagir au mouvement de la souris.

- À chaque mouvement de souris, afficher les coordonnées `(x, y)`.



## **Exercice 12 – Mini-projet 1 : Formulaire Complet**

**Objectif** : Combiner Labels, Entrys, Radiobuttons, Checkbuttons, et Bouton.

- Créer un formulaire :
  - Nom, Prénom (Entry)
  - Genre (Radiobutton)
  - Langages connus (Checkbutton)
- Ajouter un bouton "Envoyer" :
  - Quand on clique dessus, afficher **tout le contenu** en console.



## **Exercice 13 – Mini-projet 2 : Saisie et calcul simple**

**Objectif** : Utiliser Entry pour effectuer un calcul.

- Créer deux zones `Entry` :
  - Entier 1
  - Entier 2
- Ajouter un bouton "Additionner"
- Afficher la somme dans un `Label` sous les champs.



## **Exercice 14 – Mini-projet 3 : Jeu de couleur**

**Objectif** : Changer la couleur de fond de la fenêtre.

- Créer un `OptionMenu` avec plusieurs couleurs.
- Quand l'utilisateur choisit une couleur, changer la couleur du fond (`root.config(bg=...)`).



## **Exercice 15 – Projet Final : Interface "Caisse enregistreuse"**

**Objectif** : Interface semi-complète simulant l'achat de produits.

- `Listbox` avec produits (par ex : "Pain", "Lait", "Oeufs")
- `Entry` pour quantité
- Bouton "Ajouter au panier"
- Affichage dynamique du prix total
- Bouton "Payer" qui affiche un message de confirmation.



# **Progression Résumée**

| Niveau | Projet Principal |
|:------:|:----------------:|
| Débutant | Labels, Boutons simples |
| Intermédiaire | Saisie utilisateur, Listbox, Radiobuttons |
| Avancé | Interface complète avec calculs et interactions multiples |

