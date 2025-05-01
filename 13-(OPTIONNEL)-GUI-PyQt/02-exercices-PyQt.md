













## Exercice 1 – Créer une fenêtre avec QMainWindow

### Correction

```python
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow

class MaFenetre(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("Exercice 1 – Fenêtre simple")
        self.setGeometry(100, 100, 400, 200)

if __name__ == '__main__':
    app = QApplication(sys.argv)
    fenetre = MaFenetre()
    fenetre.show()
    sys.exit(app.exec_())
```

### Ce qu’on a ajouté dans cet exercice :

1. Création d’une classe héritée de `QMainWindow`.
2. Définition du titre de la fenêtre avec `.setWindowTitle()`.
3. Définition des dimensions et de la position avec `.setGeometry()`.

### Énoncé de l’exercice :

Créer une fenêtre PyQt5 avec une structure orientée objet basée sur `QMainWindow`.  
Définir un titre et une taille de 400x200 pixels.

---

## Exercice 2 – Ajouter un bouton qui modifie un label

### Correction

```python
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow, QPushButton, QLabel

class FenetreBouton(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("Exercice 2 – Bouton et Label")
        self.setGeometry(100, 100, 400, 200)

        self.label = QLabel("Texte initial", self)
        self.label.move(150, 60)

        self.bouton = QPushButton("Changer le texte", self)
        self.bouton.move(130, 100)
        self.bouton.clicked.connect(self.changer_texte)

    def changer_texte(self):
        self.label.setText("Texte modifié !")

if __name__ == '__main__':
    app = QApplication(sys.argv)
    fenetre = FenetreBouton()
    fenetre.show()
    sys.exit(app.exec_())
```

### Ce qu’on a ajouté dans cet exercice :

1. Un `QLabel` positionné dans la fenêtre.
2. Un `QPushButton` avec une action connectée.
3. Une méthode `changer_texte()` qui modifie dynamiquement le texte du label.

### Énoncé de l’exercice :

Ajouter un bouton et une étiquette dans une fenêtre.  
Lorsqu’on clique sur le bouton, le texte du label doit être modifié dynamiquement.

---

## Exercice 3 – Créer un mini formulaire avec validation

### Correction

```python
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow, QLabel, QPushButton, QLineEdit

class Formulaire(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("Exercice 3 – Formulaire simple")
        self.setGeometry(100, 100, 400, 200)

        self.label_nom = QLabel("Votre nom :", self)
        self.label_nom.move(50, 40)

        self.champ_nom = QLineEdit(self)
        self.champ_nom.move(150, 40)

        self.label_resultat = QLabel("", self)
        self.label_resultat.move(50, 130)

        self.btn_valider = QPushButton("Valider", self)
        self.btn_valider.move(150, 80)
        self.btn_valider.clicked.connect(self.afficher_nom)

    def afficher_nom(self):
        texte = self.champ_nom.text()
        if texte.strip():
            self.label_resultat.setText("Bonjour " + texte)
        else:
            self.label_resultat.setText("Veuillez entrer un nom.")

if __name__ == '__main__':
    app = QApplication(sys.argv)
    fenetre = Formulaire()
    fenetre.show()
    sys.exit(app.exec_())
```

### Ce qu’on a ajouté dans cet exercice :

1. Un `QLineEdit` pour la saisie du nom.
2. Un bouton qui déclenche une fonction de validation.
3. Un `QLabel` affichant un message personnalisé ou une erreur si le champ est vide.

### Énoncé de l’exercice :

Créer un petit formulaire avec :
- un champ pour entrer le nom,
- un bouton "Valider",
- un message qui s’affiche sous le bouton si le champ est vide ou affiche "Bonjour <nom>" si le champ est rempli.






## Exercice 4 – Interface Designer + interaction

### Prérequis

Créer une interface avec **Qt Designer** contenant :
- un `QLineEdit` (nommé `lineEdit`)
- un `QPushButton` (nommé `pushButton`)
- un `QLabel` (nommé `label`)

Sauvegarder le fichier sous le nom : `interface.ui`

---

### Correction (Python)

```python
import sys
from PyQt5 import uic
from PyQt5.QtWidgets import QApplication, QMainWindow

class FenetreDesigner(QMainWindow):
    def __init__(self):
        super().__init__()
        uic.loadUi("interface.ui", self)

        self.pushButton.clicked.connect(self.afficher)

    def afficher(self):
        nom = self.lineEdit.text()
        if nom.strip():
            self.label.setText(f"Bonjour {nom}")
        else:
            self.label.setText("Champ vide")

if __name__ == "__main__":
    app = QApplication(sys.argv)
    fenetre = FenetreDesigner()
    fenetre.show()
    sys.exit(app.exec_())
```

### Ce qu’on a ajouté dans cet exercice :

1. Chargement d’une interface `.ui` générée par Qt Designer via `uic.loadUi(...)`.
2. Accès aux composants par leur nom (`lineEdit`, `label`, `pushButton`).
3. Liaison entre le bouton et une méthode personnalisée pour interagir avec les champs.

### Énoncé de l’exercice :

Avec Qt Designer, créer une interface contenant :
- une zone de texte (`QLineEdit`)
- un bouton
- un label pour l’affichage

Dans le script Python, charger l’interface `.ui` et afficher "Bonjour <nom>" dans le label au clic du bouton.

---

## Exercice 5 – Mini-projet : calculatrice simple (addition)

### Correction

```python
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow, QLabel, QPushButton, QLineEdit

class Calculatrice(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("Exercice 5 – Addition")
        self.setGeometry(100, 100, 400, 200)

        self.entree1 = QLineEdit(self)
        self.entree1.move(50, 30)

        self.entree2 = QLineEdit(self)
        self.entree2.move(200, 30)

        self.bouton = QPushButton("Calculer", self)
        self.bouton.move(150, 70)
        self.bouton.clicked.connect(self.calculer)

        self.resultat = QLabel("Résultat :", self)
        self.resultat.move(150, 120)

    def calculer(self):
        try:
            a = float(self.entree1.text())
            b = float(self.entree2.text())
            self.resultat.setText(f"Résultat : {a + b}")
        except ValueError:
            self.resultat.setText("Entrée invalide")

if __name__ == "__main__":
    app = QApplication(sys.argv)
    fenetre = Calculatrice()
    fenetre.show()
    sys.exit(app.exec_())
```

### Ce qu’on a ajouté dans cet exercice :

1. Deux zones de saisie pour les nombres (`QLineEdit`).
2. Une gestion d’exception pour éviter les erreurs d’entrée.
3. Un bouton déclenchant une addition et affichant le résultat.

### Énoncé de l’exercice :

Créer une interface avec deux zones de saisie pour des nombres, un bouton "Calculer", et un label qui affiche la somme.  
Afficher un message d’erreur si l’une des deux entrées n’est pas un nombre.

---

## Exercice 6 – Mini-projet : formulaire de contact

### Correction

```python
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow, QLabel, QPushButton, QLineEdit, QTextEdit

class ContactForm(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("Exercice 6 – Formulaire de contact")
        self.setGeometry(100, 100, 450, 300)

        QLabel("Nom :", self).move(30, 30)
        self.nom = QLineEdit(self)
        self.nom.move(100, 30)

        QLabel("Email :", self).move(30, 70)
        self.email = QLineEdit(self)
        self.email.move(100, 70)

        QLabel("Message :", self).move(30, 110)
        self.message = QTextEdit(self)
        self.message.setGeometry(100, 110, 300, 100)

        self.btn = QPushButton("Envoyer", self)
        self.btn.move(180, 230)
        self.btn.clicked.connect(self.envoyer)

        self.label_resultat = QLabel("", self)
        self.label_resultat.move(100, 260)

    def envoyer(self):
        if self.nom.text().strip() and self.email.text().strip():
            self.label_resultat.setText("Message envoyé.")
        else:
            self.label_resultat.setText("Veuillez remplir tous les champs obligatoires.")

if __name__ == "__main__":
    app = QApplication(sys.argv)
    fenetre = ContactForm()
    fenetre.show()
    sys.exit(app.exec_())
```

### Ce qu’on a ajouté dans cet exercice :

1. Un champ `QTextEdit` pour le message.
2. Un formulaire structuré avec plusieurs champs.
3. Une validation minimale pour s’assurer que nom et email sont renseignés.
4. Une simulation d'envoi avec retour utilisateur.

### Énoncé de l’exercice :

Créer une interface de formulaire de contact avec :
- un champ pour le nom
- un champ pour l’email
- une grande zone pour écrire un message  
Ajouter un bouton "Envoyer" qui affiche un message de confirmation si tous les champs sont remplis.

