# **Interface Tkinter pas à pas**

## Objectifs

* Créer un environnement virtuel Python
* Lancer une première interface Tkinter
* Ajouter progressivement des composants (Label, Entry, Button)
* Comprendre la logique événementielle de Tkinter


## **Étape 0 – Préparation de l’environnement**

1. Créer un dossier nommé `tp_tkinter_base`.
2. Depuis le terminal, créer un environnement virtuel Python.

```bash
......................................................
```

3. Activer l’environnement virtuel.

```bash
......................................................
```

4. Installer Tkinter.

```bash
......................................................
```

5. Créer un fichier `main.py` dans ce dossier.



## **Étape 1 – Créer une fenêtre vide**

> Écris ici le code minimal permettant d’afficher une fenêtre vide intitulée "Ma première fenêtre" de taille 300x200.

```python
......................................................
......................................................
......................................................
......................................................
```


## **Étape 2 – Ajouter un Label**

> Modifie le fichier `main.py` pour qu’un `Label` contenant le texte `"Bonjour, Tkinter !"` apparaisse au centre de la fenêtre.

```python
......................................................
......................................................
......................................................
```



## **Étape 3 – Ajouter un champ de texte**

> Ajoute un champ de texte `Entry` sous le `Label`.

```python
......................................................
......................................................
```



## **Étape 4 – Ajouter un bouton**

> Ajoute un bouton intitulé "Valider" qui, lorsqu’on clique dessus, récupère le contenu du champ de texte et l’affiche dans le `Label`.

1. Écris la fonction appelée lors du clic :

```python
def afficher_message():
    ......................................................
    ......................................................
```

2. Puis ajoute le bouton :

```python
......................................................
```



## **Étape 5 – Vider le champ de texte après validation**

> Modifie la fonction `afficher_message()` pour qu’elle vide le champ `Entry` après l’affichage.

```python
def afficher_message():
    ......................................................
    ......................................................
    ......................................................
```



## **Structure attendue du fichier `main.py` final (optionnelle)**

> Si tu veux, recopie ci-dessous tout ton fichier `main.py` une fois complété.

```python
......................................................
......................................................
......................................................
......................................................
......................................................
......................................................
```











<br/>
<br/>










## **Étape 6 – Restreindre la saisie avec une condition simple**


Tu vas maintenant apprendre à **contrôler ce que l’utilisateur peut taper** dans le champ de texte.
Tu vas faire en sorte que :

* L’utilisateur **ne puisse entrer que des lettres**
* Le texte saisi ne dépasse pas **10 caractères**
* Toute autre saisie sera automatiquement **rejetée** (non affichée dans le champ)


#### 6.1 – Ajouter une fonction de validation

> Crée une fonction appelée `valider_texte` qui recevra un texte (celui que l’utilisateur essaie d’écrire).
> Cette fonction devra retourner `True` si le texte est correct, et `False` s’il contient autre chose que des lettres, ou s’il est trop long.

```python
def valider_texte(texte):
    # Vérifier que le texte contient seulement des lettres (sans chiffres, sans symboles)
    # et qu’il ne dépasse pas 10 caractères
    if ......................................................:
        return True
    else:
        return False
```

---

#### 6.2 – Enregistrer cette fonction pour Tkinter

> Tkinter a besoin que tu **enregistres** cette fonction pour pouvoir l'utiliser dans `validatecommand`.

```python
valide = root.register(......................................................)
```

---

#### 6.3 – Appliquer la validation au champ `Entry`

> Modifie ton champ `Entry` pour utiliser la validation à chaque frappe (`validate="key"`), et pour appeler ta fonction enregistrée.

```python
champ = tk.Entry(root,
                 validate="key",
                 validatecommand=(valide, "%P"))
champ.pack()
```

---

### Ce que tu dois observer :

* Si tu tapes un **mot uniquement avec des lettres**, il s’affiche.
* Si tu tapes un chiffre ou un symbole, **rien ne se passe** (la frappe est bloquée).
* Si tu dépasses 10 lettres, **la frappe est aussi bloquée**.








<br/>
<br/>





## **Étape 7 – Afficher un message et changer la couleur du champ**



Tu vas maintenant **améliorer l'expérience utilisateur** en ajoutant :

* Un **message** qui indique si la saisie est correcte ou non
* Un **changement de couleur du champ** selon le résultat



### Étapes détaillées

#### 7.1 – Créer une variable pour le message

> Crée une variable `StringVar()` pour afficher un message dynamique (texte modifiable).

```python
message = ......................................................
```



#### 7.2 – Créer un `Label` qui utilise cette variable

> Ce `Label` affichera un message en dessous du champ, selon la saisie.

```python
label_message = tk.Label(root, textvariable=message)
label_message.pack()
```


#### 7.3 – Créer une fonction appelée **après chaque frappe**

> Cette fonction va :
>
> * Vérifier si le texte dans le champ est correct
> * Mettre un message (ex : "Saisie correcte" ou "Erreur")
> * Changer la couleur du champ (`white` ou `misty rose`)

```python
def verifier_texte(event):
    texte = champ.get()
    
    # Vérifie si le texte est composé uniquement de lettres et ne dépasse pas 10 caractères
    if ......................................................:
        message.set("Saisie correcte.")
        champ.config(bg="white")
    else:
        message.set("Erreur : lettres uniquement, 10 caractères max.")
        champ.config(bg="misty rose")
```


#### 7.4 – Lier cette fonction au champ

> Grâce à `bind`, tu peux exécuter cette fonction **après chaque frappe** dans le champ.

```python
champ.bind("<KeyRelease>", ................................)
```

---

### Ce que tu dois observer :

* Le **champ reste vide** si la saisie est invalide (bloqué par `validate`)
* Mais le **message** en dessous s’actualise à chaque frappe
* Si le texte est valide → fond blanc, message "Saisie correcte."
* Si le texte est invalide → fond rosé, message d’erreur









<br/>
<br/>





# **Étape 8 – Ajouter un bouton "Effacer"**



Tu vas maintenant ajouter un **deuxième bouton**, appelé **"Effacer"**, qui :

* Vide le contenu du champ `Entry`
* Efface le message affiché
* Réinitialise la couleur du champ (en blanc)



#### 8.1 – Créer une fonction `effacer_champ`

> Cette fonction doit :
>
> * Vider le champ de texte
> * Effacer le message
> * Remettre la couleur du champ à blanc (`white`)

```python
def effacer_champ():
    ......................................................
    ......................................................
    ......................................................
```



#### 8.2 – Créer le bouton "Effacer"

> Ce bouton doit appeler la fonction `effacer_champ` quand on clique dessus.

```python
bouton_effacer = tk.Button(root, text="Effacer", command=................................)
bouton_effacer.pack()
```



### Ce que tu dois observer :

* Après avoir tapé du texte (correct ou incorrect), tu peux cliquer sur **Effacer**
* Le champ de saisie devient vide
* Le fond du champ redevient blanc
* Le message en dessous disparaît



### Vérifications à faire :

* Que se passe-t-il si tu tapes une erreur, puis cliques sur Effacer ?
* Que se passe-t-il si tu tapes un texte valide, puis cliques sur Effacer ?
* Le champ et le message sont-ils bien réinitialisés ?




