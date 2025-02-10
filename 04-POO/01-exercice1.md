### **Exercice : Manipulation des objets en Python**

#### **Objectif**
L’objectif de cet exercice est de vous entraîner à manipuler des classes et des objets en Python. Vous allez instancier plusieurs objets à partir d’une classe, modifier leurs propriétés et observer les changements.

#### **Énoncé**
Étant donné la classe `Voiture` définie ci-dessous :

```python
# Déclaration de la classe Voiture
class Voiture:
    def __init__(self, marque="Ford", modele="Mustang", annee=2020, couleur="rouge"):
        self.marque = marque
        self.modele = modele
        self.annee = annee
        self.couleur = couleur
        self.moteur_allume = False

# Instanciation de la première voiture
voiture1 = Voiture()

# Affichage initial
print("La marque de la voiture 1 est :", voiture1.marque)
print("Le modèle de la voiture 1 est :", voiture1.modele)

print("=====================================================")

# Modification 1 de voiture1
voiture1.marque = "Volkswagen"
voiture1.modele = "Beetle"
print("Modification 1 de Voiture1 :")
print("Nouvelle marque :", voiture1.marque)
print("Nouveau modèle :", voiture1.modele)
```

Vous devez effectuer les actions suivantes :

1. **Créer une deuxième voiture (`voiture2`)**  
   - Instancier un nouvel objet `voiture2` avec des valeurs différentes.
   - Modifier **au moins deux propriétés** de `voiture2` (ex: couleur, année, marque, etc.).
   - Afficher toutes les informations de `voiture2` après modification.

2. **Modifier deux fois `voiture1`**  
   - Modifier **au moins deux propriétés** de `voiture1` une première fois et afficher ses nouvelles valeurs.
   - Modifier **encore une fois au moins deux propriétés** de `voiture1` et afficher les nouvelles valeurs.

3. **Créer une troisième voiture (`voiture3`)**  
   - Instancier un nouvel objet `voiture3` avec des valeurs différentes.
   - Afficher toutes les informations de `voiture3`.

---

### **Liste des modifications à réaliser**
Étant donné la table suivante, appliquez les modifications aux objets correspondants :

| Étape | Voiture  | Propriété modifiée  | Ancienne valeur          | Nouvelle valeur |
|-------|---------|--------------------|--------------------------|-----------------|
| 1     | Voiture1 | Marque             | Ford                     | Volkswagen      |
| 2     | Voiture1 | Modèle             | Mustang                  | Beetle          |
| 3     | Voiture2 | Marque             | Ford (par défaut)        | Tesla          |
| 4     | Voiture2 | Modèle             | Mustang (par défaut)     | Model 3        |
| 5     | Voiture2 | Année              | 2020 (par défaut)        | 2022           |
| 6     | Voiture2 | Couleur            | Rouge (par défaut)       | Blanc          |
| 7     | Voiture1 | Marque (Modification 1) | Volkswagen       | BMW           |
| 8     | Voiture1 | Modèle (Modification 1) | Beetle           | X5            |
| 9     | Voiture1 | Année (Modification 1) | 2020             | 2019          |
| 10    | Voiture1 | Couleur (Modification 1) | Rouge         | Bleu          |
| 11    | Voiture1 | Marque (Modification 2) | BMW              | Audi          |
| 12    | Voiture1 | Modèle (Modification 2) | X5               | A4            |
| 13    | Voiture1 | Année (Modification 2) | 2019             | 2021          |
| 14    | Voiture1 | Couleur (Modification 2) | Bleu           | Noir          |
| 15    | Voiture3 | Marque             | Ford (par défaut)        | Toyota         |
| 16    | Voiture3 | Modèle             | Mustang (par défaut)     | Corolla        |
| 17    | Voiture3 | Année              | 2020 (par défaut)        | 2023           |
| 18    | Voiture3 | Couleur            | Rouge (par défaut)       | Gris           |

---

### **Votre mission**
- Complétez le code en respectant les étapes de la table ci-dessus.
- Affichez les informations après chaque modification.
- Assurez-vous que chaque modification est bien prise en compte.

Bonne chance ! 🚗💨
