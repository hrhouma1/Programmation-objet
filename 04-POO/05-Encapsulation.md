# **📖 L'histoire de Yahya et Georges : L'Encapsulation en Python**

Un jour, deux étudiants, **Yahya** et **Georges**, ont reçu leurs notes à l'examen.  

- **Yahya** a obtenu **70 points**  
- **Georges** a obtenu **98 points**  

Mais Yahya, voyant que Georges avait une **note bien plus élevée**, a voulu **modifier les notes** en secret :  

❌ Il voulait **baisser la note de Georges à 60** et **augmenter la sienne à 100**.  

Mais cette fois, **le professeur** a protégé les notes et **lui seul** peut les modifier.  
Pour être **juste**, il décide **d'ajouter +10 points** à chaque étudiant au lieu de laisser Yahya tricher.  

---

## **Exemple 1 : Sans Encapsulation (Problème)**
Dans cette première version, **les notes sont publiques**, donc **Yahya peut les modifier librement**.

```python
class Etudiant:
    def __init__(self, nom, note):
        self.nom = nom
        self.note = note  # Attribut public

# Création des étudiants
yahya = Etudiant("Yahya", 70)
georges = Etudiant("Georges", 98)

# Yahya modifie directement les notes
yahya.note = 100  # Il triche et met 100 pour lui-même
georges.note = 60  # Il baisse la note de Georges

# Affichage des résultats
print(f"{yahya.nom} a maintenant {yahya.note} points.")
print(f"{georges.nom} a maintenant {georges.note} points.")  
```

### 🔴 **Problème** :
➡️ **N'importe qui peut modifier les notes**, ce qui **n'est pas sécurisé**.  
➡️ Yahya peut **tricher sans aucune restriction**.  

---

## **Exemple 2 : Avec Encapsulation (Protection des Données)**
Nous allons **cacher les notes** en les rendant **privées (`__note`)**. Cela empêche Yahya de les modifier directement.

```python
class Etudiant:
    def __init__(self, nom, note):
        self.nom = nom
        self.__note = note  # Attribut privé (Encapsulation)

# Création des étudiants
yahya = Etudiant("Yahya", 70)
georges = Etudiant("Georges", 98)

# Yahya tente de modifier les notes (ça ne marche pas !)
# yahya.__note = 100  # Cela ne change pas la vraie note !
# georges.__note = 60  # Cela ne fonctionne pas non plus !

# Affichage des résultats
print(f"{yahya.nom} a {yahya._Etudiant__note} points.")  # Accès forcé (mauvaise pratique)
print(f"{georges.nom} a {georges._Etudiant__note} points.")  
```

### ✅ **Progrès : Yahya ne peut pas modifier les notes directement !**
➡️ **Les notes sont protégées** et **ne peuvent plus être modifiées n’importe comment**.  
➡️ **Mais** on peut encore **forcer l'accès** avec `_Etudiant__note`, ce qui **n'est pas recommandé**.  

---

## **Exemple 3 : Avec Getters et Setters (Le Professeur Contrôle les Notes)**
Maintenant, nous allons **offrir un accès contrôlé** aux notes avec des méthodes spéciales **`get_note()` et `set_note()`**.  

Dans cette version, **seul le professeur peut modifier les notes**, et il décide **d’ajouter +10 points** à chaque étudiant **plutôt que de laisser Yahya tricher**.

```python
class Etudiant:
    def __init__(self, nom, note):
        self.nom = nom
        self.__note = note  # Attribut privé

    def get_note(self):
        """Retourne la note de l'étudiant."""
        return self.__note

    def set_note(self, nouvelle_note):
        """Seul le professeur peut modifier les notes de manière contrôlée."""
        if 0 <= nouvelle_note <= 100:
            self.__note = nouvelle_note
        else:
            print(f"⚠️ Erreur : La note de {self.nom} doit être entre 0 et 100.")

    def ajouter_points_professeur(self, points):
        """Le professeur décide d'ajouter des points équitablement."""
        nouvelle_note = self.__note + points
        if nouvelle_note > 100:
            nouvelle_note = 100  # Limite à 100 max
        self.__note = nouvelle_note

# Création des étudiants
yahya = Etudiant("Yahya", 70)
georges = Etudiant("Georges", 98)

# Le professeur ajoute +10 points à chaque étudiant
yahya.ajouter_points_professeur(10)
georges.ajouter_points_professeur(10)

# Affichage sécurisé
print(f"{yahya.nom} a maintenant {yahya.get_note()} points.")
print(f"{georges.nom} a maintenant {georges.get_note()} points.")
```

---

### ✅ **Résultat : Un accès contrôlé aux notes !**
✔️ **Impossible de modifier les notes directement.**  
✔️ **Seules les valeurs valides sont acceptées.**  
✔️ **Le professeur contrôle les modifications et assure l'équité.**  

---

## **📝 Conclusion : L'Encapsulation, un Bouclier pour les Données**
L'**encapsulation** est **une armure pour protéger les données**.  
- **Sans encapsulation**, Yahya pouvait **tout modifier** facilement.  
- **Avec un attribut privé**, il ne peut plus **accéder aux notes directement**.  
- **Avec des getters et setters**, on contrôle **comment** les notes peuvent être modifiées.  
- **Avec une méthode spécifique (`ajouter_points_professeur()`), seul le professeur peut modifier les notes**.

👉 **Moralité :**  
Si tu veux **protéger tes données** et **éviter la triche**, utilise **l’encapsulation !** 🎯
