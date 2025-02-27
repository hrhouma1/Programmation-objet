# 1 - Différence entre **attribut d'instance** et **attribut de classe** en programmation orientée objet :  

```python
class Voiture:
    # Attribut de classe (commun à toutes les instances)
    nombre_de_roues = 4  
    
    def __init__(self, marque, couleur):
        # Attributs d'instance (propres à chaque instance)
        self.marque = marque  
        self.couleur = couleur  

# Création de deux instances de la classe Voiture
voiture1 = Voiture("Toyota", "Rouge")
voiture2 = Voiture("BMW", "Bleu")

# Affichage des attributs d'instance
print(f"Voiture 1: Marque = {voiture1.marque}, Couleur = {voiture1.couleur}")
print(f"Voiture 2: Marque = {voiture2.marque}, Couleur = {voiture2.couleur}")

# Affichage de l'attribut de classe
print(f"Voiture 1: Nombre de roues = {voiture1.nombre_de_roues}")
print(f"Voiture 2: Nombre de roues = {voiture2.nombre_de_roues}")

# Modification de l'attribut de classe via la classe
Voiture.nombre_de_roues = 6

# Vérification après modification
print(f"Voiture 1 (après modif): Nombre de roues = {voiture1.nombre_de_roues}")
print(f"Voiture 2 (après modif): Nombre de roues = {voiture2.nombre_de_roues}")

# Modification de l'attribut de classe via une instance (création d'un attribut d'instance du même nom)
voiture1.nombre_de_roues = 8  

# Vérification après modification depuis une instance
print(f"Voiture 1 (modif depuis instance): Nombre de roues = {voiture1.nombre_de_roues}")
print(f"Voiture 2 (toujours affecté par l'attribut de classe): Nombre de roues = {voiture2.nombre_de_roues}")
```

### Explication :
1. **Attribut de classe (`nombre_de_roues`)** :
   - Il appartient à la classe et est partagé par toutes les instances.
   - Modifier l'attribut de classe via la classe (`Voiture.nombre_de_roues = 6`) affecte **toutes** les instances.

2. **Attributs d'instance (`marque`, `couleur`)** :
   - Chaque instance possède ses propres valeurs pour ces attributs.

3. **Modification via une instance** :
   - Lorsque `voiture1.nombre_de_roues = 8` est exécuté, Python crée un **nouvel attribut d'instance** `nombre_de_roues` pour `voiture1` uniquement, sans modifier l'attribut de classe.

💡 **Conclusion** :
- Un **attribut de classe** est partagé entre toutes les instances.
- Un **attribut d'instance** est propre à chaque objet.
- Si une instance modifie un attribut de classe via `self`, un **nouvel attribut d'instance** est créé pour cette instance spécifique, sans affecter les autres objets.





#  2 - Différence entre une **méthode d'instance** et une **méthode de classe** en programmation orientée objet :  

```python
class Voiture:
    # Attribut de classe (commun à toutes les instances)
    nombre_de_roues = 4  
    
    def __init__(self, marque, couleur):
        # Attributs d'instance (propres à chaque instance)
        self.marque = marque  
        self.couleur = couleur  

    # Méthode d'instance (agit sur une instance spécifique)
    def afficher_info(self):
        return f"Marque: {self.marque}, Couleur: {self.couleur}, Roues: {self.nombre_de_roues}"

    # Méthode de classe (agit sur la classe entière, pas sur une instance)
    @classmethod
    def modifier_nombre_de_roues(cls, nombre):
        cls.nombre_de_roues = nombre  # Modifie l'attribut de classe

# Création de deux instances
voiture1 = Voiture("Toyota", "Rouge")
voiture2 = Voiture("BMW", "Bleu")

# Utilisation de la méthode d'instance
print("Méthodes d'instance:")
print(voiture1.afficher_info())  # Affecte uniquement voiture1
print(voiture2.afficher_info())  # Affecte uniquement voiture2

# Utilisation de la méthode de classe pour modifier l'attribut de classe
print("\nAvant modification du nombre de roues:")
print(f"Voiture 1: {voiture1.nombre_de_roues} roues")
print(f"Voiture 2: {voiture2.nombre_de_roues} roues")

Voiture.modifier_nombre_de_roues(6)  # Modification pour toutes les instances

print("\nAprès modification du nombre de roues avec la méthode de classe:")
print(f"Voiture 1: {voiture1.nombre_de_roues} roues")
print(f"Voiture 2: {voiture2.nombre_de_roues} roues")
```

### Explication :
1. **Méthode d'instance (`afficher_info`)** :
   - Utilise `self` pour accéder aux attributs de l'instance.
   - Chaque instance possède ses propres valeurs (`marque`, `couleur`).
   - Elle est appelée sur une instance spécifique (`voiture1.afficher_info()`).

2. **Méthode de classe (`modifier_nombre_de_roues`)** :
   - Utilise `cls` pour manipuler la classe entière.
   - Elle modifie l'attribut de classe (`nombre_de_roues`), ce qui affecte **toutes** les instances.
   - Elle est appelée via la classe (`Voiture.modifier_nombre_de_roues(6)`) ou une instance (`voiture1.modifier_nombre_de_roues(6)` mais cela reste une modification globale).

💡 **Conclusion** :
- Une **méthode d'instance** agit sur une **instance spécifique**.
- Une **méthode de classe** agit sur la **classe entière** et peut modifier des attributs partagés.

