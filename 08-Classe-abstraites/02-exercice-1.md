# **Exercice : Comprendre les Classes Abstraites avec des Professeurs**

## **Contexte**
Dans une école, chaque professeur enseigne une matière spécifique. Cependant, tous les professeurs partagent des caractéristiques communes :
- Ils doivent obligatoirement **donner un cours**.
- Ils doivent obligatoirement **préparer une évaluation** pour les élèves.
- Chaque professeur a une **spécialité** qui correspond à sa matière d'enseignement.

Plutôt que de définir ces éléments séparément pour chaque type de professeur, nous allons utiliser **une classe abstraite `Professeur`** pour imposer ces règles aux différentes spécialités.

---

## **Consignes**
1. **Créer une classe abstraite `Professeur`** qui définit :
   - Une méthode abstraite `donner_cours()` que chaque professeur doit implémenter pour expliquer sa matière.
   - Une méthode abstraite `preparer_evaluation()` qui décrit comment le professeur prépare un test pour les élèves.
   - Une propriété abstraite `specialite` qui indique la matière enseignée.

2. **Créer trois sous-classes concrètes** qui héritent de `Professeur` :
   - `ProfHistoire` : Ce professeur donne des cours d’histoire et prépare des dissertations.
   - `ProfInformatique` : Ce professeur donne des cours d’informatique et prépare des exercices de programmation.
   - `ProfSport` : Ce professeur donne des cours de sport et prépare des épreuves physiques.

3. **Instancier ces trois professeurs et tester leurs méthodes** :
   - Afficher le cours donné par chaque professeur.
   - Afficher la façon dont chaque professeur prépare une évaluation.
   - Afficher la spécialité de chaque professeur.

---

## **Exemple de Résultat Attendu**
Après avoir complété l’exercice, votre programme devrait produire un résultat similaire à ceci :

```python
Professeur d'Histoire donne un cours : "Aujourd'hui, nous allons étudier la Révolution Française."
Professeur d'Histoire prépare une évaluation : "Les élèves devront rédiger une dissertation sur Napoléon Bonaparte."
Spécialité du professeur : Histoire

Professeur d'Informatique donne un cours : "Aujourd'hui, nous allons apprendre la programmation en Python."
Professeur d'Informatique prépare une évaluation : "Les élèves devront coder un programme qui trie une liste de nombres."
Spécialité du professeur : Informatique

Professeur de Sport donne un cours : "Aujourd'hui, nous allons pratiquer le sprint de 100m."
Professeur de Sport prépare une évaluation : "Les élèves seront chronométrés sur un parcours d'obstacles."
Spécialité du professeur : Sport
```

---

## **Objectifs Pédagogiques**
✔ Comprendre le rôle des **classes abstraites**.  
✔ Apprendre à **forcer l’implémentation de certaines méthodes** dans les sous-classes.  
✔ Appliquer le concept d’**héritage en POO**.  
✔ Écrire un code **structuré et réutilisable**.

---

## **Bonus (Optionnel)**
- Ajouter une méthode `corriger_evaluation()` dans `Professeur` qui doit être implémentée différemment selon chaque spécialité.
- Ajouter une liste `eleves` et une méthode `ajouter_eleve(nom)` dans `Professeur`, pour suivre les élèves d’un professeur.

---

### **Travail à rendre**
📌 **Un fichier Python `professeurs.py` contenant la classe abstraite `Professeur` et ses trois sous-classes.**  
📌 **Un script de test qui crée les trois professeurs et affiche les résultats attendus.**

---

### **Bon courage !** 💡
