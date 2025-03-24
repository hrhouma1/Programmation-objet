---
# Partie 1
---

- https://forms.office.com/r/678Cm5UPAn


---
# Partie 2: Création de votre Propre Classe Abstraite en Python
---

1. **Proposez une classe abstraite de votre choix** qui pourrait être utile pour modéliser un concept précis (par exemple : `InstrumentMusical`, `AppareilElectronique`, `MoyenDeTransport`, etc.).  
2. Votre classe abstraite doit contenir **au moins trois méthodes abstraites**.   
3. Créez **au moins deux classes concrètes** qui héritent de cette classe abstraite et implémentent toutes les méthodes abstraites.   
4. Testez votre code en créant des objets de ces classes concrètes et en appelant leurs méthodes.  



# **Contraintes supplémentaires :**  
- Vous devez soumettre un fichier `.py` contenant **votre propre conception de classe abstraite et ses implémentations**.  
- **Si le même code est soumis par plusieurs étudiants, cela sera considéré comme du plagiat.**  
- Soyez original ! Trouvez une idée intéressante et réaliste.  


### **Exemple d'inspiration:**  

```python
from abc import ABC, abstractmethod

class AppareilElectronique(ABC):
    @abstractmethod
    def allumer(self):
        pass
    
    @abstractmethod
    def eteindre(self):
        pass
    
    @abstractmethod
    def recharger(self):
        pass

class Telephone(AppareilElectronique):
    def allumer(self):
        print("Le téléphone s'allume.")

    def eteindre(self):
        print("Le téléphone s'éteint.")

    def recharger(self):
        print("Le téléphone est en charge.")

class Ordinateur(AppareilElectronique):
    def allumer(self):
        print("L'ordinateur démarre.")

    def eteindre(self):
        print("L'ordinateur s'éteint.")

    def recharger(self):
        print("L'ordinateur est branché au secteur.")
        

# Test du code
mon_telephone = Telephone()
mon_telephone.allumer()
mon_telephone.recharger()

mon_ordinateur = Ordinateur()
mon_ordinateur.allumer()
mon_ordinateur.eteindre()
```



###  **À Rendre :**  

- Un court **document texte expliquant votre choix de concept abstrait et pourquoi vous l'avez choisi**.
 

