### **Code avec une distinction claire entre paramètre et attribut**
```python
class Chien:
    """
    Classe représentant un chien avec un nom et une race.
    Par défaut, le chien s'appelle 'Bob' et sa race est 'Inconnue'.
    """

    def __init__(self, myname="Bob", mybreed="Inconnue"):
        """
        Constructeur de la classe Chien.
        :param myname: Paramètre temporaire pour le nom du chien.
        :param mybreed: Paramètre temporaire pour la race du chien.
        """
        self.nom = myname  # Attribut permanent
        self.race = mybreed  # Attribut permanent

    def aboyer(self):
        """Affiche un message indiquant que le chien aboie."""
        print(f"{self.nom} aboie : Woof Woof !")

    def afficher_info(self):
        """Affiche les informations du chien."""
        print(f"Nom : {self.nom}, Race : {self.race}")


# Création de plusieurs chiens avec et sans valeurs personnalisées
chien1 = Chien()  # Utilise les valeurs par défaut
chien2 = Chien("Rex", "Labrador")
chien3 = Chien("Bella", "Berger Allemand")

# Affichage des informations et interaction
chien1.afficher_info()
chien1.aboyer()

chien2.afficher_info()
chien2.aboyer()

chien3.afficher_info()
chien3.aboyer()
```

---

### 🛠 **Explication claire pour un débutant**
1. **Paramètres (`myname`, `mybreed`)** :
   - Ce sont les valeurs **fournies** lors de l'instanciation de l'objet (`Chien("Rex", "Labrador")`).
   - Ils **existent uniquement** dans la fonction `__init__`.

2. **Attributs (`self.nom`, `self.race`)** :
   - Ce sont les valeurs **stockées dans l'objet** et accessibles après sa création.
   - Ces valeurs sont utilisées dans d'autres méthodes comme `aboyer()` et `afficher_info()`.

---

### 📌 **Différence entre Paramètres et Attributs en mémoire**
| Type | Existence | Portée |
|------|----------|--------|
| **Paramètre (`myname`, `mybreed`)** | Temporaire | Seulement dans `__init__` |
| **Attribut (`self.nom`, `self.race`)** | Permanent | Accessible dans tout l'objet |

---

### 🎯 **Résultat attendu**
```
Nom : Bob, Race : Inconnue
Bob aboie : Woof Woof !
Nom : Rex, Race : Labrador
Rex aboie : Woof Woof !
Nom : Bella, Race : Berger Allemand
Bella aboie : Woof Woof !
```

---

### 🏆 **Résumé final**
- **Paramètre (`myname`, `mybreed`)** → utilisé pour **transmettre** une valeur au moment de la création.
- **Attribut (`self.nom`, `self.race`)** → utilisé pour **stocker** cette valeur et la réutiliser plus tard.

Ce code est maintenant parfaitement adapté pour un débutant ! 🚀🐶
