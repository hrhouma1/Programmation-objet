### Vulgarisation du concept de **décorateurs** en Python

Les **décorateurs** sont un concept avancé en Python, mais ils peuvent être expliqués de manière simple. Avant de parler du décorateur `@property` et de `@setter`, il faut comprendre **ce qu'est un décorateur**.

---

## 📌 **Qu'est-ce qu'un décorateur en Python ?**
Un **décorateur** est une fonction spéciale qui modifie le comportement d'une autre fonction **sans modifier son code source**. C'est comme un "super pouvoir" qu'on donne à une fonction !

💡 **Analogie simple** :
Imagine un sandwich 🥪. Normalement, tu mets du pain, du jambon et du fromage. Mais si tu veux un sandwich **toasté**, tu peux le passer dans une machine à sandwich 🏷️ *sans changer les ingrédients*. C'est ce que fait un **décorateur** : il modifie ce qui se passe quand tu exécutes une fonction **sans la réécrire**.

---

## 📌 **Le décorateur `@property` en Python**
Dans les classes, on utilise souvent des **attributs privés** (`__email`) pour empêcher l'accès direct aux données sensibles. Mais comment lire et modifier ces données proprement ?

On utilise `@property` pour transformer une méthode en **attribut accessible directement**.

### **Sans `@property` :**
```python
class Utilisateur:
    def __init__(self, email):
        self.__email = email  # Attribut privé

    def get_email(self):
        return self.__email  # Méthode pour obtenir l'email

user = Utilisateur("test@example.com")
print(user.get_email())  # On appelle une méthode au lieu d'un attribut
```

➡️ Ce code fonctionne, mais `get_email()` ressemble à une **fonction**, alors que **l'email devrait être un simple attribut**.

### **Avec `@property` :**
```python
class Utilisateur:
    def __init__(self, email):
        self.__email = email

    @property  # Décorateur qui transforme la méthode en attribut
    def email(self):
        return self.__email

user = Utilisateur("test@example.com")
print(user.email)  # On peut l'utiliser comme un attribut !
```
✅ **Avantage** : On accède à `email` comme un **attribut normal**, sans `()`.

---

## 📌 **Le décorateur `@setter`**
Mais maintenant, comment modifier l'email **tout en validant l'adresse** ?  
On utilise `@email.setter` !

### **Avec `@setter` :**
```python
class Utilisateur:
    def __init__(self, email):
        self.__email = email

    @property
    def email(self):
        return self.__email

    @email.setter  # Décorateur qui permet de modifier l'attribut
    def email(self, email):
        if ".com" not in email and ".ca" not in email:
            print("Nouveau courriel invalide!")
        else:
            self.__email = email  # On met à jour l'attribut

# Test
user = Utilisateur("test@example.com")
print(user.email)  # Affiche : test@example.com

user.email = "nouveau@mail.com"  # ✅ Modification acceptée
print(user.email)  

user.email = "adresse_invalide"  # ❌ Erreur affichée : "Nouveau courriel invalide!"
```

✅ **Avantage** : `@setter` permet **d'empêcher des valeurs incorrectes** d'être assignées !

---

## 📌 **Correction et amélioration du code original**
Ton code contient plusieurs erreurs de syntaxe et de logique. Voici une version **corrigée et améliorée** :

```python
class Utilisateur:
    def __init__(self, email):
        self.__email = email

    @property
    def email(self):
        """Getter pour l'email."""
        return self.__email

    @email.setter
    def email(self, email):
        """Setter avec validation d'email."""
        if ".com" in email or ".ca" in email:
            self.__email = email
        else:
            print("Nouveau courriel invalide!")

# Test
user = Utilisateur("test@example.com")
print(user.email)  # Affiche : test@example.com

user.email = "nouveau@mail.ca"  # ✅ Modification acceptée
print(user.email)  

user.email = "adresse_invalide"  # ❌ Affiche : "Nouveau courriel invalide!"
```

---

## 📌 **Résumé final**
- `@property` permet d'accéder à un attribut privé **comme un attribut normal**.
- `@setter` permet **de modifier l'attribut tout en le contrôlant**.
- **Avantage** : On protège les données et on évite des erreurs de modification.

💡 **Astuce pour s'en souvenir** :  
👉 **Getter = Lire** (`@property`)  
👉 **Setter = Modifier** (`@email.setter`)

---

## 📌 **Challenge final pour tester leur compréhension**
Demande aux étudiants d'améliorer cette classe en ajoutant un attribut **âge** avec :
- `@property` pour lire l'âge.
- `@setter` qui empêche les âges négatifs ou trop élevés (ex: >120 ans).

💡 **Correction attendue :**
```python
class Utilisateur:
    def __init__(self, email, age):
        self.__email = email
        self.__age = age

    @property
    def email(self):
        return self.__email

    @email.setter
    def email(self, email):
        if ".com" in email or ".ca" in email:
            self.__email = email
        else:
            print("Nouveau courriel invalide!")

    @property
    def age(self):
        return self.__age

    @age.setter
    def age(self, age):
        if 0 <= age <= 120:
            self.__age = age
        else:
            print("Âge invalide!")

# Test
user = Utilisateur("test@example.com", 25)
print(user.age)  # 25

user.age = 150  # ❌ "Âge invalide!"
```

Ainsi, ils deviennent **des cadécorateurs** ! 🚀
