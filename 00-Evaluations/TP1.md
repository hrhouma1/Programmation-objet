# **TP : Modélisation et Gestion d’un Laboratoire de Recherche en POO (avec Encapsulation)**

## **Contexte et objectifs**  
Dans ce travail pratique, vous allez modéliser un **laboratoire de recherche** en appliquant les principes de la **Programmation Orientée Objet (POO)** en Python. Vous devez respecter les concepts suivants :

- **Encapsulation** : certains attributs sont **privés** et doivent être accessibles uniquement via des **getters et setters**.  
- **Distinction entre attributs d’instance et attributs de classe** : certains attributs doivent être partagés entre toutes les instances.  
- **Gestion cohérente des objets** : chaque classe doit avoir des relations bien définies avec les autres classes.  

Ce TP est **noté sur 100 points** et doit être structuré de manière claire et fonctionnelle.

---

## **1. Classe Adresse (15 points)**  
### **Attributs à implémenter**
| Attribut      | Portée  | Description |
|--------------|--------|-------------|
| `etat`       | **Public**  | État de l’adresse (ex: "New York") |
| `ville`      | **Public**  | Ville de l’adresse (ex: "Manhattan") |
| `__code_postal` | **Privé**  | Code postal, accessible uniquement via getter et setter (ex: "10001") |

### **Méthodes à implémenter**
1. **Encapsulation (5 points)**
   - Implémenter un **getter** `get_code_postal()` qui renvoie le code postal.
   - Implémenter un **setter** `set_code_postal(nouveau_code)` qui modifie le code postal uniquement si la valeur est valide.

2. **Affichage (5 points)**
   - Implémentez la méthode `__str__()`, qui retourne :  
     ```
     Manhattan, New York - 10001
     ```
3. **Code final(5 points)**
- Donnez le code final de la classe Adresse.
  
---

## **2. Classe Chercheur (20 points)**  
### **Attributs à implémenter**
| Attribut      | Portée  | Description |
|--------------|--------|-------------|
| `nom`        | **Public**  | Nom du chercheur (ex: "Dr. Smith") |
| `poste`      | **Public**  | Poste du chercheur (ex: "Professeur") |
| `__num_ordinateur` | **Privé**  | Numéro d’ordinateur du chercheur, accessible uniquement via getter et setter (ex: "PC001") |

### **Méthodes à implémenter**
1. **Encapsulation (5 points)**
   - Implémenter un **getter** `get_num_ordinateur()` qui renvoie le numéro d’ordinateur.
   - Implémenter un **setter** `set_num_ordinateur(nouveau_num)` qui modifie le numéro d’ordinateur uniquement si la valeur est valide.

2. **Affichage (5 points)**
   - Implémentez la méthode `__str__()`, qui retourne :  
     ```
     Dr. Smith, Professeur, PC001
     ```

3. **Code final(5 points)**
- Donnez le code final de la classe Chercheur.

  
3. **Héritage (5 points)**
   - Implémentez une classe `Professeur` qui hérite de `Chercheur` et ajoute un attribut privé `__specialite` (ex: "Intelligence Artificielle").  
   - Implémentez les getters et setters correspondants.
   - Donnez le code final de la classe Professeur.

---

## **3. Classe Bureau (25 points)**  
### **Attributs à implémenter**
| Attribut      | Portée  | Description |
|--------------|--------|-------------|
| `code`       | **Public**  | Code du bureau (ex: "B001") |
| `nom`        | **Public**  | Nom du bureau (ex: "Machine Learning") |
| `__chercheurs` | **Privé**  | Liste des chercheurs présents dans le bureau |
| `MAX_CHERCHEURS` | **Attribut de classe** | Nombre maximal de chercheurs par bureau (5) |

### **Méthodes à implémenter**
1. **Gestion des chercheurs (5 points)**
   - Implémentez `ajouter_chercheur(chercheur)` qui ajoute un chercheur si la limite `MAX_CHERCHEURS` n’est pas atteinte.
   - Affichez un message d’erreur si le bureau est plein.

2. **Encapsulation (5 points)**
   - La liste `__chercheurs` est privée.  
   - Implémentez une méthode `get_chercheurs()` pour obtenir la liste.

3. **Affichage (5 points)**
   - Implémentez `afficher_bureau()` qui retourne :  
     ```
     Bureau Machine Learning (B001):
     Dr. Smith, Professeur, PC001
     Dr. Johnson, Chercheur, PC002
     ```

4. **Code final(10 points)**
- Donnez le code final de la classe Bureau.
  
---

## **4. Classe Laboratoire (25 points)**  
### **Attributs à implémenter**
| Attribut      | Portée  | Description |
|--------------|--------|-------------|
| `nom`        | **Public**  | Nom du laboratoire (ex: "NY Tech Lab") |
| `specialite` | **Public**  | Spécialité du laboratoire (ex: "Intelligence Artificielle") |
| `adresse`    | **Public**  | Instance de la classe `Adresse` |
| `__bureaux`  | **Privé**  | Liste des bureaux présents dans le laboratoire |
| `MAX_BUREAUX` | **Attribut de classe** | Nombre maximal de bureaux par laboratoire (50) |

### **Méthodes à implémenter**
1. **Gestion des bureaux (5 points)**
   - Implémentez `ajouter_bureau(bureau)` qui ajoute un bureau si la limite `MAX_BUREAUX` n’est pas atteinte.
   - Affichez un message d’erreur si le laboratoire est plein.

2. **Encapsulation (5 points)**
   - La liste `__bureaux` est privée.  
   - Implémentez une méthode `get_bureaux()` pour obtenir la liste.

3. **Affichage (5 points)**
   - Implémentez `afficher_laboratoire()` qui retourne :  
     ```
     NY Tech Lab - Intelligence Artificielle
     Adresse: Manhattan, New York - 10001

     Bureau Machine Learning (B001):
     Dr. Smith, Professeur, PC001
     Dr. Johnson, Chercheur, PC002
     ```

4. **Code final(10 points)**
- Donnez le code final de la classe Laboratoire.
  
---

## **5. Mise en Œuvre et Résultat Final (15 points)**  
1. **Création et manipulation des instances (10 points)**  
   - Créez et reliez les objets suivants :
     - `Adresse("New York", "Manhattan", "10001")`
     - `Chercheur("Dr. Smith", "Professeur", "PC001")`
     - `Bureau("B001", "Machine Learning")`, auquel vous ajoutez `Dr. Smith`
     - `Laboratoire("NY Tech Lab", "Intelligence Artificielle", adresse)`, auquel vous ajoutez `Bureau B001`
   - Assurez-vous que chaque instance respecte bien ses contraintes (ex : un chercheur ne peut pas être ajouté à plus de 5 bureaux).

2. **Affichage final (5 points)**  
   - Vérifiez que la méthode `afficher_laboratoire()` donne bien le résultat attendu.

---

## **Barème récapitulatif**

| Section                      | Points |
|------------------------------|--------|
| **Classe `Adresse`**         | 15     |
| **Classe `Chercheur`**       | 20     |
| **Classe `Bureau`**         | 25     |
| **Classe `Laboratoire`**     | 25     |
| **Mise en Œuvre et Tests**   | 15     |
| **Total**                    | **100** |

---

## **Consignes de Rendu**
1. **Code bien structuré et commenté**  
   - Chaque classe doit être définie dans un fichier unique (`adresse.py`, `chercheur.py`, `bureau.py`, `laboratoire.py`).  
   - Un fichier principal (`main.py`) doit tester et afficher les résultats demandés.  

2. **Validation de l’encapsulation et du respect des limites**  
   - **Testez vos getters et setters** en tentant d’accéder aux attributs privés.  
   - **Ajoutez des messages d’erreur** lorsque les limites (`MAX_CHERCHEURS`, `MAX_BUREAUX`) sont dépassées.  

**Bon travail à toutes et à tous !** Assurez-vous que votre code fonctionne et respecte les principes de la POO et de l’encapsulation. 
