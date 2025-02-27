

### **1. `adresse.py`**
```python
class Adresse:
    def __init__(self, rue: str, ville: str, code_postal: str):
        self.rue = rue
        self.ville = ville
        self.__code_postal = None  
        self.set_code_postal(code_postal)  

    def get_code_postal(self) -> str:
        return self.__code_postal

    def set_code_postal(self, nouveau_code: str):
        if isinstance(nouveau_code, str) and len(nouveau_code) == 5 and nouveau_code.isdigit():
            self.__code_postal = nouveau_code
        else:
            print("Erreur : Code postal invalide (5 chiffres requis).")

    def __str__(self) -> str:
        return f"{self.rue}, {self.ville} - {self.__code_postal}"
```

---

### **2. `hopital.py`**
```python
class Hopital:
    MAX_SERVICES = 20  

    def __init__(self, nom: str, adresse):
        self.nom = nom
        self.adresse = adresse
        self.__services = []

    def ajouter_service(self, service):
        if len(self.__services) < self.MAX_SERVICES:
            self.__services.append(service)
        else:
            print("Erreur : Limite de services atteinte.")

    def get_services(self):
        return self.__services

    def afficher_hopital(self):
        print(f"{self.nom}\nAdresse : {self.adresse}\nServices médicaux :")
        for service in self.__services:
            print(f"- {service.nom}")
```

---

### **3. `service_medical.py`**
```python
class ServiceMedical:
    MAX_MEDECINS = 10
    MAX_PATIENTS = 50

    def __init__(self, nom: str):
        self.nom = nom
        self.__medecins = []
        self.__patients = []

    def ajouter_medecin(self, medecin):
        if len(self.__medecins) < self.MAX_MEDECINS:
            self.__medecins.append(medecin)
        else:
            print("Erreur : Trop de médecins dans ce service.")

    def ajouter_patient(self, patient):
        if len(self.__patients) < self.MAX_PATIENTS:
            self.__patients.append(patient)
        else:
            print("Erreur : Trop de patients dans ce service.")

    def afficher_service(self):
        print(f"\nService : {self.nom}")
        print("Médecins :")
        for medecin in self.__medecins:
            print(f"- {medecin}")
        print("Patients :")
        for patient in self.__patients:
            print(f"- {patient}")
```

---

### **4. `medecin.py`**
```python
class Medecin:
    def __init__(self, nom: str, matricule: str, service):
        self.nom = nom
        self.__matricule = None
        self.service = service
        self.set_matricule(matricule)

    def get_matricule(self) -> str:
        return self.__matricule

    def set_matricule(self, nouveau_matricule: str):
        if isinstance(nouveau_matricule, str) and nouveau_matricule.startswith("M") and nouveau_matricule[1:].isdigit():
            self.__matricule = nouveau_matricule
        else:
            print("Erreur : Matricule invalide (ex: M001).")

    def __str__(self) -> str:
        return f"{self.nom} ({self.__matricule}) - Service : {self.service.nom}"


class Chirurgien(Medecin):
    def __init__(self, nom: str, matricule: str, service, specialite: str):
        super().__init__(nom, matricule, service)
        self.specialite = specialite

    def __str__(self) -> str:
        return f"{self.nom} ({self.get_matricule()}) - Chirurgien {self.specialite} - Service : {self.service.nom}"
```

---

### **5. `patient.py`**
```python
from dossier_medical import DossierMedical

class Patient:
    def __init__(self, nom: str, age: int, dossier_medical):
        self.nom = nom
        self.age = age
        self.__dossier_medical = dossier_medical

    def get_dossier_medical(self):
        return self.__dossier_medical

    def __str__(self) -> str:
        return f"{self.nom} ({self.age} ans)"
```

---

### **6. `dossier_medical.py`**
```python
class DossierMedical:
    def __init__(self, numero_dossier: str, antecedents_medicaux: list, traitements: list):
        self.numero_dossier = numero_dossier
        self.antecedents_medicaux = antecedents_medicaux
        self.traitements = traitements

    def __str__(self) -> str:
        return (f"Dossier Médical : {self.numero_dossier}\n"
                f"Antécédents : {', '.join(self.antecedents_medicaux)}\n"
                f"Traitements : {', '.join(self.traitements)}")
```

---

### **7. `main.py` (fichier de test)**
```python
from adresse import Adresse
from hopital import Hopital
from service_medical import ServiceMedical
from medecin import Medecin, Chirurgien
from patient import Patient
from dossier_medical import DossierMedical

# Création de l'Adresse
adresse_hopital = Adresse("10 rue de la Santé", "Paris", "75014")

# Création de l’Hôpital
hopital = Hopital("Hôpital Saint-Louis", adresse_hopital)

# Création des Services Médicaux
service_cardiologie = ServiceMedical("Cardiologie")
service_urgences = ServiceMedical("Urgences")

# Ajout des services à l’hôpital
hopital.ajouter_service(service_cardiologie)
hopital.ajouter_service(service_urgences)

# Création des Médecins
medecin1 = Medecin("Dr. Martin", "M001", service_cardiologie)
medecin2 = Medecin("Dr. Dubois", "M002", service_urgences)
chirurgien1 = Chirurgien("Dr. Dupont", "M003", service_cardiologie, "Chirurgie Cardiaque")

# Ajout des médecins aux services
service_cardiologie.ajouter_medecin(medecin1)
service_cardiologie.ajouter_medecin(chirurgien1)
service_urgences.ajouter_medecin(medecin2)

# Création des Patients
dossier1 = DossierMedical("12345", ["Hypertension"], ["Bêtabloquants"])
dossier2 = DossierMedical("67890", ["Diabète"], ["Insuline"])

patient1 = Patient("Pierre Dupont", 45, dossier1)
patient2 = Patient("Marie Curie", 30, dossier2)

# Ajout des patients aux services
service_cardiologie.ajouter_patient(patient1)
service_urgences.ajouter_patient(patient2)

# Affichage des informations
print("\n=== Informations de l’Hôpital ===")
hopital.afficher_hopital()

print("\n=== Détails des Services ===")
service_cardiologie.afficher_service()
service_urgences.afficher_service()

print("\n=== Détails des Médecins ===")
print(medecin1)
print(medecin2)
print(chirurgien1)

print("\n=== Détails des Patients ===")
print(patient1)
print(patient2)

print("\n=== Détails des Dossiers Médicaux ===")
print(patient1.get_dossier_medical())
print(patient2.get_dossier_medical())
```

---

## **Instructions pour Google Colab**
1. **Créer un fichier par classe** (`adresse.py`, `hopital.py`, etc.).
2. **Copier-coller les codes ci-dessus dans chaque fichier correspondant.**
3. **Exécuter `main.py`** dans une cellule Colab pour tester.

