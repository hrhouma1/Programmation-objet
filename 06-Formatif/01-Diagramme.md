### ** Diagramme**
```
                             +--------------------+
                             |     Adresse        |
                             +--------------------+
                             | - rue              |
                             | - ville            |
                             | - __code_postal    |
                             +--------------------+
                             | + get_code_postal()|
                             | + set_code_postal()|
                             | + __str__()        |
                             +--------------------+
                                    ▲
                                    |
                    +--------------------------------+
                    |          Hopital              |
                    +--------------------------------+
                    | - nom                          |
                    | - adresse (Adresse)           |
                    | - __services (list)           |
                    | - MAX_SERVICES (20)           |
                    +--------------------------------+
                    | + ajouter_service()           |
                    | + get_services()              |
                    | + afficher_hopital()          |
                    +--------------------------------+
                                    ▲
                                    |
                  +--------------------------------+
                  |        Service Médical        |
                  +--------------------------------+
                  | - nom                          |
                  | - __medecins (list)            |
                  | - __patients (list)            |
                  | - MAX_MEDECINS (10)            |
                  | - MAX_PATIENTS (50)            |
                  +--------------------------------+
                  | + ajouter_medecin()           |
                  | + ajouter_patient()           |
                  | + afficher_service()          |
                  +--------------------------------+
                                    ▲
                 -----------------------------------
                 |                                 |
                 |  (RELATIONS DE COMPOSITION)    |
                 |                                 |
+-------------------------------+     +---------------------------+
|          Médecin              |     |          Patient           |
+-------------------------------+     +---------------------------+
| - nom                          |     | - nom                     |
| - __matricule                  |     | - age                     |
| - service (Service Médical)     |     | - __dossier_medical (DossierMedical) |
+-------------------------------+     +---------------------------+
| + get_matricule()             |     | + get_dossier_medical()   |
| + set_matricule()             |     | + __str__()               |
| + __str__()                   |     +---------------------------+
                 ▲                                   ▲
                 |                                   |
            (HÉRITAGE)                            (COMPOSITION)
                 |                                   |
  ------------------------------------             +---------------------------+
  |                                  |             |       Dossier Médical      |
  |                                  |             +---------------------------+
  |                                  |             | - numero_dossier           |
  |                                  |             | - antecedents_medicaux     |
  |                                  |             | - traitements              |
  |                                  |             +---------------------------+
  |                                  |             | + get_antecedents()        |
  |                                  |             | + get_traitements()        |
  |                                  |             | + __str__()                |
  |                                  |             +---------------------------+
+-------------------------------+     +---------------------------+
|         Chirurgien            |     |         Infirmier         |
+-------------------------------+     +---------------------------+
| - specialite                  |     | - __identifiant           |
+-------------------------------+     | - service (Service Médical)|
| + get_specialite()             |     +---------------------------+
| + set_specialite()             |     | + get_identifiant()        |
| + __str__() (override)         |     | + set_identifiant()        |
+-------------------------------+     | + __str__()                 |
                                       +---------------------------+
```



# **Explication détaillée de l'héritage et des relations**

## **Héritage (séparé en haut)**
- `Chirurgien` et `Infirmier` héritent de `Médecin`.  
  - **Chirurgien** ajoute l’attribut `specialite`.  
  - **Infirmier** ajoute l’attribut `__identifiant`.  

## **Relations de composition (partie basse du diagramme)**
- Un `Patient` a un `Dossier Médical`, qui est une relation de **composition** (le dossier médical n’existe que s’il y a un patient).  
- Un `Médecin` appartient à un `Service Médical`.  
- Un `Service Médical` appartient à un `Hopital`.  

## Flèches: 

- **Les flèches vers le haut indiquent l’héritage**.  
- **Les flèches vers le bas indiquent la composition et les relations d’agrégation**.  
