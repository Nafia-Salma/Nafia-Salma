# Application de Gestion de Notes

Cette application est une application web fullstack conçue pour gérer des notes personnelles avec une expérience utilisateur immersive. L'application permet aux utilisateurs de créer, modifier, supprimer et afficher des notes, avec la possibilité d'ajouter des tags pour une meilleure organisation. L'authentification est mise en œuvre avec JWT, garantissant l'accès sécurisé et privé à l'application.

## Table des Matières

1. [Aperçu du Projet](#aperçu-du-projet)
2. [Fonctionnalités](#fonctionnalités)
3. [Conception et UX](#conception-et-ux)
4. [Instructions d'Installation](#instructions-dinstallation)
5. [Exécution de l'Application](#exécution-de-lapplication)
6. [Documentation de l'API](#documentation-de-lapi)
7. [Captures d'Écran](#captures-decran)
8. [Observations Techniques](#observations-techniques)

---

### Aperçu du Projet

Ce projet est une application de prise de notes développée avec Django (backend) et React (frontend). L'objectif principal de l'application est d'offrir une expérience utilisateur fluide et intuitive. Les utilisateurs peuvent créer, gérer et supprimer des notes avec des tags qui leur sont spécifiques. L'application garantit la confidentialité en exigeant des identifiants de connexion pour accéder à la page d'accueil et aux notes.

### Fonctionnalités

- **Page d'Accueil** : Affiche une liste de toutes les notes de l'utilisateur connecté. Chaque note apparaît sous forme de carte, et en survolant une note, des icônes pour l'édition ou la suppression s'affichent.
- **Ajouter une Nouvelle Note** : Un bouton en haut de la page d'accueil ouvre une fenêtre pop-up pour créer une nouvelle note, avec des options pour ajouter des tags ou créer de nouveaux tags.
- **Tags** : Les tags sont spécifiques à chaque utilisateur et aident à classer les notes. Les utilisateurs peuvent ajouter ou créer des tags directement dans la fenêtre de création de note.
- **Authentification** :
  - Pages de **Connexion** et **Inscription** avec authentification basée sur JWT.
  - La connexion redirige vers la page d'accueil, tandis que l'inscription redirige vers la page de connexion.
  - L'accès à la page d'accueil est restreint aux utilisateurs authentifiés uniquement.
  - La fonction de déconnexion efface les identifiants et redirige vers la page de connexion.
  - Jeton d'accès de courte durée avec une expiration de 30 minutes.
- **Gestion des Erreurs** : Une page "Non Trouvée" est affichée pour les URL inexistantes.

### Conception et UX

L'interface utilisateur (UI) et l'expérience utilisateur (UX) sont conçues pour être simples, engageantes et visuellement immersives. Les décisions de conception suivantes ont été mises en œuvre :

- **Navigation Intuitive** : La barre de navigation comprend des liens vers la page d'accueil, la connexion, l'inscription et la déconnexion.
- **Retour d'Information Utilisateur** : Chaque action de l'utilisateur (par exemple, édition, suppression) est reconnue visuellement pour une expérience utilisateur réactive.
- **Effets de Survol** : En survolant les notes, des icônes interactives pour les options d'édition et de suppression apparaissent, garantissant des actions claires.
- **Gestion des Erreurs** : Des messages d'erreur conviviaux et une page "Non Trouvée" améliorent l'expérience utilisateur en cas d'actions non intentionnelles.

L'ensemble du design de l'interface a été d'abord créé dans Figma, en mettant l'accent sur la facilité d'utilisation et une expérience immersive.

### Instructions d'Installation

1. **Cloner le Répertoire** :
   ```bash
   git clone <url_du_répertoire>
   cd note-management-app
   ```

2. **Configuration du Backend (Django)** :
   - Assurez-vous d'avoir Python installé, puis créez un environnement virtuel :
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```
   - Installez les packages requis :
     ```bash
     pip install -r requirements.txt
     ```
   - Exécutez les migrations et créez un super utilisateur :
     ```bash
     python manage.py migrate
     python manage.py createsuperuser
     ```
   - Démarrez le serveur Django :
     ```bash
     python manage.py runserver
     ```

3. **Configuration du Frontend (React)** :
   - Naviguez vers le répertoire frontend :
     ```bash
     cd frontend
     ```
   - Installez les dépendances :
     ```bash
     npm install
     ```
   - Démarrez le serveur React :
     ```bash
     npm start
     ```

### Exécution de l'Application

Pour exécuter l'application, démarrez d'abord le serveur Django, puis démarrez le serveur frontend React. L'application sera accessible à l'adresse `http://localhost:3000`.

### Documentation de l'API

Les API de cette application ont été créées à l'aide de Django REST Framework et sont disponibles via Insomnia et Swagger.

1. **Documentation Swagger** :
   - Accédez à la documentation Swagger à `http://localhost:8000/swagger/`.
   - Cette documentation fournit un aperçu de chaque point de terminaison avec des détails sur l'utilisation et des exemples de requêtes.

2. **Test des APIs avec Insomnia** :
   - Toutes les APIs ont été testées dans Insomnia, où les réponses, les codes d'état et la validation des données ont été vérifiés.
   - Des captures d'écran des requêtes et réponses API sont disponibles pour référence.

### Captures d'Écran

Voici des captures d'écran pour présenter la fonctionnalité et la conception de l'application :

1. **Page d'Accueil** :
   - Affiche toutes les notes avec des effets de survol pour les icônes d'édition et de suppression.
   ![Page d'Accueil](path/to/homepage-screenshot.png)

2. **Fenêtre Pop-Up de Création de Note** :
   - Affiche la fenêtre pop-up pour ajouter une nouvelle note, avec des options pour ajouter ou créer des tags.
   ![Ajouter Note](path/to/add-note-popup.png)

3. **Pages de Connexion et d'Inscription** :
   - Formulaires simples et sécurisés pour la connexion et l'inscription.
   ![Page de Connexion](path/to/login-page.png)
   ![Page d'Inscription](path/to/register-page.png)

4. **Panneau d'Administration Django** :
   - Fournit une vue backend pour gérer les utilisateurs, les notes et les tags.
   ![Panneau d'Administration](path/to/admin-panel.png)

5. **Swagger et Insomnia** :
   - Documentation API et exemples de tests pour référence.
   ![Swagger](path/to/swagger-doc.png)
   ![Insomnia](path/to/insomnia-tests.png)

### Observations Techniques

1. **Authentification** : 
   - Mise en œuvre de l'authentification via JWT pour sécuriser les sessions utilisateur.
   - Un jeton d'accès de courte durée (30 minutes) assure une sécurité accrue, nécessitant une nouvelle authentification après expiration.

2. **Intégration Backend-Frontend** :
   - L'API REST Django communique avec React via des requêtes Axios, garantissant un échange de données fluide entre le frontend et le backend.
   - La gestion de l'état et le routage garantissent que seuls les utilisateurs authentifiés peuvent accéder à la page d'accueil avec les fonctionnalités de gestion des notes.

3. **Animations et UX du Frontend** :
   - Mise en œuvre d'effets de survol et de messages de retour pour améliorer l'expérience utilisateur.
   - Conçu avec un accent sur l'UX pour fournir un flux clair, de la connexion à la gestion des notes.

4. **Défis de Développement** :
   - Assurer la synchronisation entre l'API REST de Django et la gestion de l'état de React a nécessité une planification minutieuse.
   - La gestion de l'expiration du JWT et des jetons de rafraîchissement a présenté une couche de complexité supplémentaire pour sécuriser les sessions utilisateur.

### Améliorations Futures

- **Collaboration en Temps Réel** : Ajouter des fonctionnalités en temps réel pour permettre le partage de notes ou l'édition collaborative.
- **Recherche et Filtrage Avancés** : Permettre aux utilisateurs de filtrer les notes par tags ou mots-clés pour faciliter la gestion des notes.
- **Gestion Avancée des Tags** : Ajouter des options pour éditer et supprimer des tags avec des mises à jour automatiques des notes associées.

---

Ce fichier README fournit un aperçu complet de l'application de gestion de notes, depuis l'installation jusqu'à l'utilisation et la conception technique.
