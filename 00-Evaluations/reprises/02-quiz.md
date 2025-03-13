## 📝 **Quiz : Programmation Orientée Objet en Python**
**Instructions** : Choisissez la bonne réponse pour chaque question.

### **Section 1 : Concepts de Base**
1️⃣ **Qu'est-ce qu'une classe en Python ?**  
   a) Une instance d'objet  
   b) Un modèle ou un plan pour créer des objets  
   c) Une méthode spéciale  
   d) Une variable globale  

2️⃣ **Quelle est la différence entre une classe et un objet ?**  
   a) Une classe est une instance d'un objet  
   b) Une classe est un plan, un objet est une instance de cette classe  
   c) Un objet est un plan, une classe est son instance  
   d) Les deux sont identiques  

3️⃣ **Quelle syntaxe est correcte pour définir une classe en Python ?**  
   a) `class MaClasse {}`  
   b) `class MaClasse:`  
   c) `define class MaClasse()`  
   d) `MaClasse = class()`  

4️⃣ **Quel est le rôle de `__init__` dans une classe Python ?**  
   a) C'est une méthode qui supprime un objet  
   b) C'est une méthode spéciale appelée automatiquement lors de la création d'un objet  
   c) C'est une méthode qui définit un attribut privé  
   d) C'est une méthode pour imprimer des informations  

### **Section 2 : Attributs et Méthodes**
5️⃣ **Comment accède-t-on à un attribut d'une instance ?**  
   a) `objet.attribut`  
   b) `self.attribut`  
   c) `objet->attribut`  
   d) `objet[attribut]`  

6️⃣ **Quel mot-clé est utilisé pour référencer l'instance courante dans une classe ?**  
   a) `this`  
   b) `instance`  
   c) `self`  
   d) `object`  

7️⃣ **Comment définit-on une méthode dans une classe en Python ?**  
   a) `def ma_methode(self):`  
   b) `method ma_methode(self):`  
   c) `function ma_methode(self):`  
   d) `def ma_methode():`  

8️⃣ **Quelle est la bonne façon d'affecter une valeur à un attribut dans une classe ?**  
   a) `self.nom = "Python"`  
   b) `nom = "Python"`  
   c) `this.nom = "Python"`  
   d) `self["nom"] = "Python"`  

### **Section 3 : Héritage et Polymorphisme**
9️⃣ **Comment hériter d'une classe en Python ?**  
   a) `class Fille(Mere):`  
   b) `class Fille <- Mere:`  
   c) `class Fille implements Mere:`  
   d) `class Fille inherit Mere:`  

🔟 **Quelle méthode est appelée lorsqu'un objet est supprimé ?**  
   a) `__del__`  
   b) `__delete__`  
   c) `__remove__`  
   d) `__destroy__`  

1️⃣1️⃣ **Quel est l'intérêt du polymorphisme en POO ?**  
   a) Il permet à une classe d'avoir plusieurs parents  
   b) Il permet d’utiliser une même interface pour différents types d’objets  
   c) Il empêche l’héritage multiple  
   d) Il supprime les méthodes inutiles  

1️⃣2️⃣ **Quelle syntaxe est correcte pour redéfinir une méthode dans une classe fille ?**  
   a) `def methode(self) override:`  
   b) `def methode(self):`  
   c) `override def methode(self):`  
   d) `methode def(self):`  

1️⃣3️⃣ **Quelle est la différence entre une méthode de classe et une méthode statique ?**  
   a) Une méthode statique ne peut pas être appelée par une instance  
   b) Une méthode de classe prend `cls` comme premier paramètre  
   c) Une méthode de classe ne peut pas accéder aux attributs de la classe  
   d) Une méthode statique modifie les instances de la classe  

### **Section 4 : Encapsulation et Propriétés**
1️⃣4️⃣ **Comment définit-on un attribut privé en Python ?**  
   a) `self.__attribut`  
   b) `self._attribut`  
   c) `self.attribut_privé`  
   d) `self.-attribut`  

1️⃣5️⃣ **Quelle est la principale utilité du décorateur `@property` ?**  
   a) Empêcher l'accès aux attributs d'une classe  
   b) Permettre un accès contrôlé aux attributs d'une classe  
   c) Rendre les attributs publics  
   d) Convertir une méthode en attribut privé  

1️⃣6️⃣ **Comment empêche-t-on une classe d’être héritée ?**  
   a) En utilisant `@final`  
   b) En déclarant la classe avec `class MonObjet final:`  
   c) En empêchant la surcharge des méthodes  
   d) En Python, ce n'est pas possible nativement  

### **Section 5 : Méthodes Spéciales et Concepts Avancés**
1️⃣7️⃣ **Quelle méthode spéciale permet de rendre un objet itérable ?**  
   a) `__iter__`  
   b) `__next__`  
   c) `__getitem__`  
   d) `__repr__`  

1️⃣8️⃣ **Que renvoie la méthode spéciale `__str__` dans une classe ?**  
   a) Une représentation lisible de l’objet  
   b) Une valeur booléenne  
   c) Une conversion en liste  
   d) Une adresse mémoire  

1️⃣9️⃣ **Comment surcharge-t-on un opérateur en Python ?**  
   a) En redéfinissant une méthode spéciale comme `__add__`  
   b) En utilisant `override`  
   c) En définissant une fonction `operator.add`  
   d) Ce n’est pas possible en Python  

2️⃣0️⃣ **Que fait la méthode spéciale `__call__` dans une classe Python ?**  
   a) Elle permet d’exécuter une instance comme une fonction  
   b) Elle supprime une instance  
   c) Elle crée un nouvel attribut  
   d) Elle initialise une instance  
