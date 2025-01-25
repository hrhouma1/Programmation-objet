# Pratique 0 - Créer un environnement virtuel en Python avec l'invite de commandes

## Introduction
Un environnement virtuel Python est un espace isolé pour installer des modules spécifiques à un projet, sans affecter l’environnement global de votre système.

---

## Étape 1 : Ouvrir l'invite de commandes
1. **Windows** :
   - Appuyez sur `Windows + R`, tapez `cmd`, puis appuyez sur **Entrée**.
   - Alternativement, tapez "Invite de commandes" dans la barre de recherche, puis appuyez sur **Entrée**.

---

## Étape 2 : Vérifier que Python et pip sont installés
1. Tapez la commande suivante pour vérifier que Python est installé :
   ```cmd
   python --version
   ```
   Si cela ne fonctionne pas, essayez :
   ```cmd
   python3 --version
   python3.9 --version
   python3.11 --version
   python3.12 --version
   python3.13 --version
   ```

2. Vérifiez également que `pip` est installé avec :
   ```cmd
   pip --version
   ```
   Si cela ne fonctionne pas, essayez :
   ```cmd
   python -m pip --version
   python3 -m pip --version
   python3.9 -m pip --version
   python3.11 -m pip --version
   python3.12 -m pip --version
   python3.13 -m pip --version
   ```

3. Si Python ou pip n’est pas installé, téléchargez et installez Python depuis le site officiel : [python.org](https://www.python.org).

---

## Étape 3 : Installer `venv` si nécessaire
1. Si le module `venv` n'est pas disponible, installez-le avec :
   ```cmd
   pip install venv
   ```

---

## Étape 4 : Accéder ou créer un dossier pour le projet
1. Accédez au répertoire souhaité. Par exemple :
   ```cmd
   cd C:\Users\VotreNom\Documents
   ```

2. Créez un dossier pour votre projet et entrez dedans :
   ```cmd
   mkdir MonProjet
   cd MonProjet
   ```

---

## Étape 5 : Créer l'environnement virtuel
1. Créez un environnement virtuel nommé `myenvironment1` (ou un autre nom de votre choix) :
   ```cmd
   python -m venv myenvironment1
   ```
   Si `python` ne fonctionne pas, utilisez :
   ```cmd
   python3 -m venv myenvironment1
   python3.9 -m venv myenvironment1
   python3.11 -m venv myenvironment1
   python3.12 -m venv myenvironment1
   python3.13 -m venv myenvironment1
   ```

2. **Résultat attendu** :
   - Un dossier nommé `myenvironment1` sera créé.
   - Ce dossier contiendra tous les fichiers nécessaires pour l’environnement virtuel.

3. Vérifiez la création avec :
   ```cmd
   dir
   ```
   Vous verrez un dossier nommé `myenvironment1`.

---

## Étape 6 : Activer l'environnement virtuel
1. Activez l’environnement virtuel avec :
   ```cmd
   myenvironment1\Scripts\activate
   ```

2. Une fois activé, le préfixe `(myenvironment1)` apparaîtra au début de chaque ligne dans l’invite de commandes :
   ```plaintext
   (myenvironment1) C:\Users\VotreNom\Documents\MonProjet>
   ```

---

## Étape 7 : Installer des packages
1. Installez un package comme `requests` dans l’environnement virtuel avec :
   ```cmd
   pip install requests
   ```

2. Vérifiez les packages installés avec :
   ```cmd
   pip list
   ```

   **Exemple de résultat attendu** :
   ```plaintext
   Package    Version
   ---------  -------
   pip        X.X.X
   requests   X.X.X
   setuptools X.X.X
   ```

---

## Étape 8 : Désactiver l'environnement virtuel
1. Une fois que vous avez terminé, désactivez l’environnement virtuel avec :
   ```cmd
   deactivate
   ```

2. Le préfixe `(myenvironment1)` disparaît. Vous êtes de retour dans l’environnement Python global.

---

## Étape 9 : Supprimer un environnement virtuel (optionnel)
1. Pour supprimer l’environnement virtuel, supprimez simplement le dossier correspondant :
   ```cmd
   rmdir /s /q myenvironment1
   ```
   - **`/s`** : supprime tous les sous-dossiers.
   - **`/q`** : supprime sans confirmation.

---

## Récapitulatif des commandes

- **Vérifier les versions de Python et pip :**
  ```cmd
  python --version
  python3 --version
  python3.9 --version
  python3.11 --version
  python3.12 --version
  python3.13 --version
  pip --version
  ```

- **Créer un dossier projet :**
  ```cmd
  mkdir NomDossier
  cd NomDossier
  ```

- **Créer un environnement virtuel :**
  ```cmd
  python -m venv NomEnvironnement
  ```

- **Activer l’environnement :**
  ```cmd
  NomEnvironnement\Scripts\activate
  ```

- **Installer des packages :**
  ```cmd
  pip install NomDuPackage
  ```

- **Vérifier les packages installés :**
  ```cmd
  pip list
  ```

- **Désactiver l’environnement :**
  ```cmd
  deactivate
  ```

- **Supprimer l’environnement :**
  ```cmd
  rmdir /s /q NomEnvironnement
  ```

---

## Pratique guidée

1. **Créer un projet :**
   - Naviguez vers le dossier souhaité :
     ```cmd
     cd C:\Users\VotreNom\Documents
     ```
   - Créez un dossier projet :
     ```cmd
     mkdir MonExercice
     cd MonExercice
     ```

2. **Créer et activer un environnement virtuel :**
   - Créez l’environnement :
     ```cmd
     python -m venv myenvironment1
     ```
   - Activez-le :
     ```cmd
     myenvironment1\Scripts\activate
     ```

3. **Installer et vérifier un package :**
   - Installez `flask` :
     ```cmd
     pip install flask
     ```
   - Vérifiez les installations :
     ```cmd
     pip list
     ```

4. **Désactiver l’environnement :**
   ```cmd
   deactivate
   ```

---

## Accessibilité

- **Vérification de l'activation :** Si le préfixe `(myenvironment1)` n’apparaît pas, exécutez une commande comme `pip list` pour confirmer que l’environnement est actif.
- **Navigation et gestion des erreurs :** Utilisez `dir` pour vérifier les fichiers et dossiers dans votre répertoire.


Avec cette pratique, vous êtes prêt à gérer efficacement des environnements virtuels pour vos projets Python !
