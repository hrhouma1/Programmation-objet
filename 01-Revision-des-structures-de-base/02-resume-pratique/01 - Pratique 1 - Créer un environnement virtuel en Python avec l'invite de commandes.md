# Pratique 1 : Créer un environnement virtuel en Python avec l'invite de commandes

## Introduction

Un environnement virtuel Python est un espace isolé où vous pouvez installer des modules ou des dépendances spécifiques à un projet, sans affecter le système global. Voici comment le créer et l'utiliser à l'aide de l'invite de commandes (CMD).

---

## Étape 1 : Ouvrir l'invite de commandes

1. **Sur Windows :**
   - Appuyez sur `Windows + R`, tapez `cmd`, puis appuyez sur **Entrée**.
   - Une fenêtre noire (invite de commandes) s’ouvre.

2. **Alternativement** :
   - Appuyez sur la touche Windows, tapez "Invite de commandes", puis appuyez sur **Entrée**.

---

## Étape 2 : Accéder ou créer un répertoire pour le projet

1. **Accédez au répertoire où vous voulez créer le projet.** Par exemple, si vous voulez travailler dans le dossier `Documents` :
   ```cmd
   cd C:\Users\VotreNom\Documents
   ```

2. **Créez un nouveau dossier pour votre projet** en tapant :
   ```cmd
   mkdir MonProjet
   cd MonProjet
   ```

   - **`mkdir`** signifie "make directory", soit "créer un dossier".
   - **`cd`** signifie "change directory", soit "changer de dossier".

   **Vous êtes maintenant dans le dossier `MonProjet`.**

---

## Étape 3 : Créer l'environnement virtuel

1. Tapez la commande suivante pour créer un environnement virtuel :
   ```cmd
   python -m venv nom_env
   ```

   - Remplacez **`nom_env`** par le nom que vous voulez donner à l’environnement virtuel. Par exemple :
     ```cmd
     python -m venv venv
     ```

2. **Résultat attendu :**
   - Cette commande crée un dossier nommé `venv` (ou le nom que vous avez choisi).
   - Ce dossier contient tous les fichiers nécessaires pour l'environnement virtuel.

3. **Vérification :**
   Tapez la commande suivante pour afficher le contenu du dossier :
   ```cmd
   dir
   ```
   Vous devriez voir un dossier nommé `venv` dans la liste.

---

## Étape 4 : Activer l'environnement virtuel

1. **Activez l’environnement virtuel** en tapant :
   ```cmd
   venv\Scripts\activate
   ```

   - Remplacez `venv` par le nom de votre environnement si vous avez choisi un autre nom.

2. Une fois activé, vous verrez le nom de l’environnement entre parenthèses au début de chaque ligne. Par exemple :
   ```plaintext
   (venv) C:\Users\VotreNom\Documents\MonProjet>
   ```

3. **Note pour les non-voyants** :
   Si vous n'entendez pas le préfixe `(venv)` via le lecteur d'écran, essayez d'exécuter une commande comme `pip list` (voir l'Étape 5). Si elle fonctionne correctement, cela confirme que l'environnement est actif.

---

## Étape 5 : Installer un package dans l'environnement virtuel

1. Pour installer un package dans l'environnement virtuel, utilisez `pip`. Par exemple, pour installer le module `requests` :
   ```cmd
   pip install requests
   ```

2. Vérifiez que le module a été installé en affichant la liste des packages :
   ```cmd
   pip list
   ```

   **Résultat attendu :**
   ```plaintext
   Package    Version
   ---------  -------
   pip        X.X.X
   requests   X.X.X
   setuptools X.X.X
   ```

3. Si cela fonctionne, vous avez configuré correctement votre environnement virtuel.

---

## Étape 6 : Désactiver l'environnement virtuel

1. Une fois que vous avez fini de travailler, désactivez l'environnement virtuel en tapant :
   ```cmd
   deactivate
   ```

2. Le préfixe `(venv)` disparaît. Vous êtes maintenant de retour dans l'environnement Python global.

---

## Étape 7 : Supprimer un environnement virtuel (optionnel)

1. Si vous souhaitez supprimer un environnement virtuel, il suffit de supprimer le dossier correspondant. Par exemple :
   ```cmd
   rmdir /s /q venv
   ```

   - **`/s`** supprime tous les sous-dossiers.
   - **`/q`** supprime sans demander confirmation.

2. Le dossier `venv` sera complètement supprimé.

---

## Pratique guidée

Suivez cette pratique pour consolider vos connaissances :

1. **Créer un projet :**
   - Ouvrez CMD.
   - Naviguez vers le dossier où vous voulez créer le projet (par exemple, `Documents`).
   - Créez un dossier appelé `MonExercice` avec :
     ```cmd
     mkdir MonExercice
     cd MonExercice
     ```

2. **Créer et activer un environnement virtuel :**
   - Créez un environnement virtuel nommé `env_test` :
     ```cmd
     python -m venv env_test
     ```
   - Activez l’environnement avec :
     ```cmd
     env_test\Scripts\activate
     ```

3. **Installer un package :**
   - Installez le package `Flask` dans l’environnement virtuel :
     ```cmd
     pip install flask
     ```

4. **Vérifier les installations :**
   - Affichez la liste des packages installés avec :
     ```cmd
     pip list
     ```

5. **Désactiver l’environnement :**
   - Tapez :
     ```cmd
     deactivate
     ```

---

## Récapitulatif des commandes

- **Créer un dossier pour un projet :**
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

- **Désactiver l’environnement :**
  ```cmd
  deactivate
  ```

---

## Accessibilité

1. **Préfixe `(venv)`** : Si vous utilisez un lecteur d'écran, vous ne verrez peut-être pas directement le préfixe. Pour confirmer que l'environnement est actif, exécutez une commande comme `pip list` pour vérifier son fonctionnement.

2. **Navigation dans les dossiers :** Utilisez les commandes comme `dir` pour entendre la liste des fichiers et dossiers.

3. **Évitez les erreurs :** Si une commande échoue, assurez-vous que vous êtes dans le bon dossier et que Python est installé correctement.

