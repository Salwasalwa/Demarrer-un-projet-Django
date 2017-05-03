# Démarrage d'un projet Django

Dans votre terminal, allez dans le dossier où vous souhaitez créer votre nouveau projet.

Création de votre environnement virtuel:
- ```virtualenv <leNomDeVotreDossier>-env```

Déplacez vous dedans:
- ```cd <leNomDeVotreDossier>-env```

Activation de votre environnement virtuel:
- ```source bin/activate```

Installation de Django:
- ```pip install django```

---
**Si vous voulez utiliser MySQL:**
- ```pip install MySQL-python```

---

Création du projet:
- ```django-admin startproject <NomDeVotreProjet>```

Déplacez vous dedans:
- ```cd <NomDeVotreProjet>```

Création du dépôt Git:
- ```git init```

Création et édition de .gitignore:
- ```sudo nano .gitignore```

Et ajouter au minimum:
- ```*.pyc```
- ```media/```
- ```*.db```
- ```*.sqlite3```

---
**Pour MySQL: Ouvrir le fichier 'settings.py', et modifier cette partie:**
```
DATABASES = {
    'default': {
        'NAME': '<NomDeVotreBDD>',
        'ENGINE': 'django.db.backends.mysql',
        'USER': '<IDENTIFIANT>',
        'PASSWORD': '<MDP>'
    }
}
```

---

Actualisation de la BDD:
- ```python manage.py migrate```

Création d'application(s):
- ```python manage.py startapp <NomDeVotreApp>```

Ajout de votre app dans le fichier settings.py, et dans le même temps, changement du fuseau horaire et de la langue:
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    '<NomDeVotreApp>',
]
```

- ```LANGUAGE_CODE = 'fr-FR'```

- ```TIME_ZONE = 'CET'```

Dans la partie TEMPLATES, copier/coller ceci entre les crochets de DIRS:
- ```os.path.join(BASE_DIR, '<NomDeVotreProjet>', 'templates')```

Création d'un dossier templates dans ```<NomDeVotreApp>```, static/css/sass, static/js et templates dans ```<NomDeVotreProjet>```:
- ```mkdir -p <NomDeVotreApp>/templates static/css/sass static/img static/js <NomDeVotreProjet>/templates```

Création du fichier urls.py dans ```<NomDeVotreApp>```
- ```touch <NomDeVotreApp>/urls.py```

---
Si vous voulez utiliser Bower:
- ```cd static```
- ```bower init```
- ```bower install <dépendance> --save```

---

Création d'un Admin:
- ```python manage.py createsuperuser```

Démarrage d'un serveur Web de développement léger sur la machine locale:
- ```python manage.py runserver <Port au choix>```


# Astuce
La commande:
- ```source bin/activate```

peut être simplifiée par:
- ```. bin/activate```

A ce sujet, pour quitter votre environnement virtuel:
- ```deactivate```

Les commandes avec python, ex:
- ```python manage.py migrate```

peuvent être simplifiées par:
- ```./manage.py migrate```
