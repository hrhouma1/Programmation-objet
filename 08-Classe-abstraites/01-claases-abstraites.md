# **Cours : Les Classes Abstraites en Python avec `ABC`**

## **Introduction**
En programmation orientée objet (POO), une **classe abstraite** est une classe qui ne peut pas être instanciée directement et qui sert de modèle pour ses classes dérivées. Elle définit des méthodes que les classes enfants doivent obligatoirement implémenter. En Python, les classes abstraites sont définies à l'aide du module `abc` avec `ABC` et `@abstractmethod`.

Ce cours va explorer en détail :
- Pourquoi utiliser des classes abstraites ?
- Comment définir et utiliser une classe abstraite en Python ?
- Un exemple concret avec des voitures

---

## **1. Pourquoi utiliser des classes abstraites ?**

### **Problème sans classe abstraite**
Imaginons que nous créons un programme qui manipule différentes voitures. Nous avons plusieurs types de voitures, comme **VoitureSport** et **VoitureUtilitaire**.

Sans classe abstraite, nous pourrions définir une classe `Voiture` et ses sous-classes, mais rien n'oblige les sous-classes à implémenter des méthodes essentielles comme `rouler()` ou `klaxonner()`. Cela peut entraîner des erreurs si une sous-classe oublie d'implémenter une méthode essentielle.

### **Solution avec une classe abstraite**
- Une classe abstraite définit une structure commune et impose aux sous-classes d'implémenter certaines méthodes essentielles.
- En Python, nous utilisons `ABC` (Abstract Base Class) pour cela.

---

## **2. Création d'une classe abstraite en Python**

### **Définition d’une classe abstraite**
En Python, une classe abstraite est définie en héritant de `ABC` et en utilisant `@abstractmethod` :

```python
from abc import ABC, abstractmethod, abstractproperty

class Voiture(ABC):  # Classe abstraite
    @abstractmethod
    def rouler(self):
        """Méthode obligatoire que toutes les sous-classes doivent implémenter"""
        pass

    @abstractmethod
    def klaxonner(self):
        """Méthode obligatoire que toutes les sous-classes doivent implémenter"""
        pass

    @abstractproperty
    def couleur(self):
        """Propriété obligatoire"""
        pass
```

### **Explications**
- `ABC` signifie **Abstract Base Class**.
- `@abstractmethod` rend obligatoire l’implémentation de la méthode dans toutes les sous-classes.
- `@abstractproperty` est utilisé pour forcer la déclaration d'une **propriété**.

On ne peut pas instancier `Voiture` directement :

```python
voiture = Voiture()  # TypeError: Can't instantiate abstract class Voiture
```

---

## **3. Création de classes concrètes**

### **Une voiture de sport**
```python
class VoitureSport(Voiture):  # Hérite de Voiture
    def rouler(self):
        return "La voiture de sport roule rapidement."

    def klaxonner(self):
        return "Beep beep !"

    @property
    def couleur(self):
        return "Rouge"

    def faire_un_tour(self):
        return "La voiture de sport fait un tour sur la piste."
```

### **Une voiture utilitaire**
```python
class VoitureUtilitaire(Voiture):  # Hérite de Voiture
    def rouler(self):
        return "La voiture utilitaire roule lentement."

    def klaxonner(self):
        return "Honk honk !"

    @property
    def couleur(self):
        return "Bleu"

    def transporter_marchandises(self):
        return "La voiture utilitaire transporte des marchandises."
```

### **Explications**
- Chaque classe concrète **hérite de `Voiture`** et **implémente obligatoirement** `rouler()`, `klaxonner()`, et `couleur`.
- Si l'on oublie d'implémenter l'une des méthodes abstraites, Python lèvera une erreur :

```python
TypeError: Can't instantiate abstract class VoitureSport with abstract methods ...
```

---

## **4. Utilisation des classes**

Créons des objets à partir de nos classes concrètes et testons leurs méthodes :

```python
voiture_sport = VoitureSport()
voiture_utilitaire = VoitureUtilitaire()

print(voiture_sport.rouler())          # Output: La voiture de sport roule rapidement.
print(voiture_sport.klaxonner())       # Output: Beep beep !
print(voiture_sport.couleur)           # Output: Rouge
print(voiture_sport.faire_un_tour())   # Output: La voiture de sport fait un tour sur la piste.

print(voiture_utilitaire.rouler())          # Output: La voiture utilitaire roule lentement.
print(voiture_utilitaire.klaxonner())       # Output: Honk honk !
print(voiture_utilitaire.couleur)           # Output: Bleu
print(voiture_utilitaire.transporter_marchandises())  # Output: La voiture utilitaire transporte des marchandises.
```

---

## **5. Avantages des classes abstraites**
Les classes abstraites sont très utiles car elles :
1. **Forcent une structure commune** dans les sous-classes.
2. **Évitent les erreurs** en obligeant l’implémentation de méthodes essentielles.
3. **Facilitent la maintenance et l’évolutivité** du code.
4. **Améliorent la lisibilité** en définissant clairement les méthodes nécessaires.

---

## **6. Différence avec une Interface**
En Python, une **interface** est souvent simulée à l'aide d'une classe abstraite avec uniquement des méthodes abstraites (pas d'implémentation).

**Classe Abstraite vs. Interface :**

| Classe Abstraite | Interface |
|--------------------|------------|
| Peut contenir des méthodes avec du code | Ne contient que des méthodes abstraites |
| Peut avoir des variables d’instance | Ne contient généralement que des méthodes |
| Peut contenir des méthodes normales et abstraites | Toutes les méthodes sont abstraites |
| Peut servir de base pour plusieurs classes avec implémentations partielles | Sert uniquement à définir un contrat |

En Python, on n’a pas de mot-clé spécifique pour les interfaces, donc les classes abstraites jouent souvent ce rôle.

---

## **7. Cas d'utilisation des classes abstraites**
Les classes abstraites sont utilisées lorsqu’on veut :
- Définir un **modèle commun** sans fournir d’implémentation.
- **Structurer des sous-classes** pour garantir qu'elles possèdent certaines méthodes.
- Empêcher l'instanciation directe d'une classe générique.

Exemples concrets :
- Un système de **paiement** (`MoyenPaiement` avec `payer()`)
- Une gestion des **animaux** (`Animal` avec `manger()` et `dormir()`)
- Un moteur de **jeu vidéo** (`Personnage` avec `attaquer()` et `défendre()`)

---

## **Conclusion**
Les classes abstraites sont un concept clé en POO permettant de structurer efficacement un programme. En Python, on les crée avec `ABC` et `@abstractmethod`. Elles sont idéales pour définir des **modèles génériques** et garantir que toutes les sous-classes implémentent certaines méthodes essentielles.

**Points à retenir :**  
- Une classe abstraite est un **modèle**.  
- Elle ne peut pas être instanciée directement.  
- Les méthodes abstraites **doivent être implémentées** dans les sous-classes.  

**Pratique :** Essayer d'implémenter d'autres types de véhicules en ajoutant des classes comme `Moto`, `Camion`, etc.
