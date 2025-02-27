# **Questions Étape par Étape : Développement du TP Gestion d’un Hôpital en POO**



## **1. Développement de la classe `Adresse` (15 points)**  
L’objectif est de créer une classe `Adresse` qui représente l'adresse d'un hôpital. Cette classe doit **protéger le code postal** en le rendant privé et accessible uniquement via des **getters et setters**.

### **Attributs à implémenter**
| Attribut         | Portée   | Description |
|-----------------|---------|-------------|
| `rue`          | **Public**  | Rue de l'adresse (ex: "10 rue de la Santé") |
| `ville`        | **Public**  | Ville de l'adresse (ex: "Paris") |
| `__code_postal` | **Privé**   | Code postal, accessible uniquement via un getter et un setter (ex: "75014") |

### **Questions**
1. Implémentez la classe `Adresse` avec un **constructeur `__init__`** prenant en paramètres la rue, la ville et le code postal.
2. Rendez l’attribut `__code_postal` **privé** et initialisez-le correctement.
3. Ajoutez un **getter `get_code_postal()`** pour récupérer le code postal.
4. Ajoutez un **setter `set_code_postal(nouveau_code)`** qui :
   - Vérifie que le **code postal est une chaîne de 5 chiffres**.
   - Affiche un **message d'erreur** si la valeur est invalide.
5. Implémentez la **méthode `__str__()`** pour afficher l'adresse sous ce format :  
   ```
   10 rue de la Santé, Paris - 75014
   ```

---

## **2. Développement de la classe `Hopital` (20 points)**  
L'objectif est de modéliser un hôpital qui possède **plusieurs services médicaux**.

### **Attributs à implémenter**
| Attribut         | Portée   | Description |
|-----------------|---------|-------------|
| `nom`          | **Public**  | Nom de l’hôpital (ex: "Hôpital Saint-Louis") |
| `adresse`      | **Public**  | Instance de la classe `Adresse` |
| `__services`   | **Privé**   | Liste des services médicaux de l’hôpital |
| `MAX_SERVICES` | **Attribut de classe** | Nombre maximal de services dans l’hôpital (20) |

### **Questions**
1. Implémentez la classe `Hopital` avec un **constructeur `__init__`**, qui prend en paramètres **le nom et une instance de `Adresse`**.
2. Ajoutez un **attribut privé `__services`**, qui est une **liste vide** au départ.
3. Ajoutez une **constante de classe `MAX_SERVICES = 20`** pour limiter le nombre de services.
4. Implémentez une méthode **`ajouter_service(service)`** qui :
   - Ajoute un service médical uniquement si la limite de `MAX_SERVICES` n'est pas atteinte.
   - Affiche un **message d'erreur** si l'hôpital est plein.
5. Implémentez une méthode **`get_services()`** qui retourne la liste des services.
6. Implémentez une méthode **`afficher_hopital()`** qui affiche :
   ```
   Hôpital Saint-Louis
   Adresse : 10 rue de la Santé, Paris - 75014
   Services médicaux :
   - Cardiologie
   - Urgences
   ```

---

## **3. Développement de la classe `ServiceMedical` (20 points)**  
Un service médical regroupe des **médecins et des patients**.

### **Attributs à implémenter**
| Attribut         | Portée   | Description |
|-----------------|---------|-------------|
| `nom`          | **Public**  | Nom du service médical (ex: "Cardiologie") |
| `__medecins`   | **Privé**   | Liste des médecins affectés au service |
| `__patients`   | **Privé**   | Liste des patients suivis par le service |
| `MAX_MEDECINS` | **Attribut de classe** | Nombre maximal de médecins (10) |
| `MAX_PATIENTS` | **Attribut de classe** | Nombre maximal de patients (50) |

### **Questions**
1. Implémentez la classe `ServiceMedical` avec un **constructeur `__init__`**, qui prend en paramètre **le nom du service**.
2. Initialisez les **attributs privés `__medecins` et `__patients`** comme des listes vides.
3. Ajoutez une **constante de classe** pour limiter le nombre de médecins et de patients (`MAX_MEDECINS = 10`, `MAX_PATIENTS = 50`).
4. Implémentez une méthode **`ajouter_medecin(medecin)`** qui :
   - Ajoute un médecin uniquement si la limite de `MAX_MEDECINS` n'est pas atteinte.
   - Affiche un **message d'erreur** si la limite est dépassée.
5. Implémentez une méthode **`ajouter_patient(patient)`** qui :
   - Ajoute un patient uniquement si la limite de `MAX_PATIENTS` n'est pas atteinte.
   - Affiche un **message d'erreur** si la limite est dépassée.
6. Implémentez une méthode **`afficher_service()`** qui affiche :
   ```
   Service : Cardiologie
   Médecins :
   - Dr. Martin
   - Dr. Dubois
   Patients :
   - Pierre Dupont
   - Marie Curie
   ```

---

## **4. Développement de la classe `Medecin` et ses sous-classes (20 points)**  
Un médecin appartient à un **service médical**.

### **Attributs à implémenter**
| Attribut         | Portée   | Description |
|-----------------|---------|-------------|
| `nom`          | **Public**  | Nom du médecin (ex: "Dr. Martin") |
| `__matricule`  | **Privé**   | Matricule unique du médecin (ex: "M001") |
| `service`      | **Public**  | Instance de `ServiceMedical` |

### **Questions**
1. Implémentez la classe `Medecin` avec un **constructeur `__init__`**, qui prend en paramètres :
   - Le **nom du médecin**.
   - Son **matricule**, qui doit être **privé**.
   - Son **service médical**.
2. Ajoutez un **getter `get_matricule()`** pour récupérer le matricule.
3. Ajoutez un **setter `set_matricule(nouveau_matricule)`** qui valide que :
   - Le matricule commence par "M" suivi de chiffres (ex: "M001").
4. Implémentez la méthode **`__str__()`** pour afficher un médecin sous cette forme :
   ```
   Dr. Martin (M001) - Service : Cardiologie
   ```
5. Créez une **classe `Chirurgien` qui hérite de `Medecin`** et ajoute l’attribut `specialite` :
   - Ajoutez un getter et un setter pour `specialite`.
   - Surchargez la méthode `__str__()` pour inclure la spécialité.

---

## **5. Développement de la classe `Patient` et `DossierMedical` (25 points)**
Un patient possède un **dossier médical**.

### **Attributs à implémenter**
| Attribut            | Portée   | Description |
|--------------------|---------|-------------|
| `nom`             | **Public**  | Nom du patient |
| `age`             | **Public**  | Âge du patient |
| `__dossier_medical` | **Privé**   | Instance de `DossierMedical` |

### **Questions**
1. Implémentez la classe `Patient` avec un **dossier médical privé**.
2. Ajoutez une méthode `get_dossier_medical()` pour récupérer le dossier.
3. Implémentez la classe `DossierMedical` avec :
   - Un numéro de dossier.
   - Les antécédents médicaux.
   - Les traitements.
4. Implémentez la méthode `__str__()` pour afficher :
   ```
   Dossier Médical : 12345
   Antécédents : Hypertension
   Traitements : Médicaments
   ```




--
# **Énoncé : Tester l'application avec `main.py`**  
---

L'objectif de cette étape est de **tester l'ensemble des classes** développées pour la gestion d'un hôpital.  
Le test doit **vérifier** :
1. La création des objets (`Adresse`, `Hopital`, `ServiceMedical`, `Médecin`, `Patient`, `DossierMedical`).
2. L'ajout et l'affectation des médecins et patients aux services médicaux.
3. L'affichage des informations pour valider la bonne structuration des données.

---

## **1. Création de l’adresse de l’hôpital**  
Créer une **instance de la classe `Adresse`** avec les valeurs suivantes :  
- Rue : `"10 rue de la Santé"`
- Ville : `"Paris"`
- Code postal : `"75014"`

---

## **2. Création de l’hôpital**  
Créer une **instance de la classe `Hopital`** en utilisant :  
- Nom : `"Hôpital Saint-Louis"`
- Adresse : `Adresse` créée à l’étape 1

---

## **3. Création de deux services médicaux**  
Créer deux **instances de la classe `ServiceMedical`** :  
1. `"Cardiologie"`
2. `"Urgences"`

Les **ajouter à l’hôpital**.

---

## **4. Création et affectation de médecins**  
Créer **trois médecins** :
1. `Médecin("Dr. Martin", "M001", service_cardiologie)`
2. `Médecin("Dr. Dubois", "M002", service_urgences)`
3. `Chirurgien("Dr. Dupont", "M003", service_cardiologie, "Chirurgie Cardiaque")`

Les **ajouter aux services** correspondants :
- `Dr. Martin` et `Dr. Dupont` dans `Cardiologie`.
- `Dr. Dubois` dans `Urgences`.

---

## **5. Création et affectation de patients**  
Créer **deux patients** :
1. `Patient("Pierre Dupont", 45, dossier1)`  
   - **Dossier médical** : numéro `12345`, antécédent `"Hypertension"`, traitement `"Bêtabloquants"`.
   - Affecté au **service Cardiologie**.
2. `Patient("Marie Curie", 30, dossier2)`  
   - **Dossier médical** : numéro `67890`, antécédent `"Diabète"`, traitement `"Insuline"`.
   - Affectée au **service Urgences**.

Les **ajouter aux services** correspondants.

---

## **6. Affichage des informations**
### **Afficher l'hôpital et ses services**  
Utiliser `hopital.afficher_hopital()` pour vérifier que :
- L’hôpital est bien créé.
- Les services médicaux sont bien associés.

### **Afficher les détails des services médicaux**  
Utiliser `service_cardiologie.afficher_service()` et `service_urgences.afficher_service()` pour vérifier :
- La liste des médecins affectés à chaque service.
- La liste des patients affectés à chaque service.

### **Afficher les médecins et les patients**  
Vérifier l'affichage des **médecins et patients** individuellement avec `print()` :
- `print(medecin1)`
- `print(medecin2)`
- `print(chirurgien1)`
- `print(patient1)`
- `print(patient2)`

### **Afficher les dossiers médicaux des patients**  
Utiliser `print(patient1.get_dossier_medical())` et `print(patient2.get_dossier_medical())` pour afficher :
- Les **numéros de dossiers médicaux**.
- Les **antécédents médicaux et traitements**.

---

## **7. Tester les limites et erreurs**
### **Ajout d’un service au-delà de la limite**
- **Ajouter 20 services à l’hôpital**, puis tenter d'en ajouter un **21e**.
- Vérifier que **l’ajout est refusé** avec un message d’erreur.

### **Ajout de médecins au-delà de la limite**
- **Ajouter 10 médecins** à un service, puis tenter d'en ajouter un **11e**.
- Vérifier que **l’ajout est refusé** avec un message d’erreur.

### **Ajout de patients au-delà de la limite**
- **Ajouter 50 patients** à un service, puis tenter d'en ajouter un **51e**.
- Vérifier que **l’ajout est refusé** avec un message d’erreur.

### **Validation des setters**
- Modifier le **code postal** avec une **valeur invalide** (`"123"`) et vérifier que le message d’erreur apparaît.
- Modifier le **matricule d’un médecin** avec une **valeur invalide** (`"X001"`) et vérifier que le message d’erreur apparaît.

---

## **Critères de validation**
✔ **Les objets sont créés correctement** (Hôpital, Services, Médecins, Patients, Dossiers).  
✔ **Les relations sont bien établies** (Médecins et Patients associés aux bons services).  
✔ **L'affichage est conforme** aux attentes.  
✔ **Les erreurs sont bien gérées** (limites dépassées, saisies invalides).  

