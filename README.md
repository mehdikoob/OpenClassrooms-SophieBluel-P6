# Sophie Bluel – Projet 6 du parcours Développeur Web (OpenClassrooms)

Ce dépôt contient le projet de portfolio d’architecte d’intérieur réalisé dans le cadre du parcours Développeur Web d’OpenClassrooms. Le but était de développer la partie front‑end d’un site présentant les réalisations de Sophie Bluel et d’implémenter un back‑end en Node.js permettant la gestion des projets via une API sécurisée.

## Description

Le projet se compose de deux parties :

- **FrontEnd** : un site statique en HTML, CSS et JavaScript qui présente les projets de décoration intérieure de Sophie Bluel. La page « portfolio » affiche une galerie d’images filtrable par catégorie (Tous, Objets, Appartement, Hôtel & Restaurants). Un bouton « login » permet d’accéder à une interface d’administration (modal) pour ajouter ou supprimer des projets.

- **Backend** : une API REST construite avec Node.js, Express et SQLite. Elle propose des routes pour récupérer les travaux (*works*) et les catégories, ainsi que des routes sécurisées pour l’authentification (JSON Web Token) et l’upload d’images via Multer. La documentation de l’API est disponible via Swagger.

## Fonctionnalités principales

- Affichage dynamique du portfolio avec filtres par catégories.
- Authentification par token pour accéder à l’interface d’administration.
- Ajout et suppression de projets via des requêtes POST/DELETE sur l’API.
- Utilisation de Sequelize pour interagir avec la base de données SQLite.
- Sécurisation des en‑têtes HTTP avec Helmet et gestion des droits via CORS.
- Documentation Swagger disponible à l’adresse `/api-docs`.

## Installation

1. Clonez le dépôt :
```bash
git clone https://github.com/mehdikoob/OpenClassrooms-SophieBluel-P6.git
```

### FrontEnd

Ouvrez le fichier `FrontEnd/index.html` dans votre navigateur. Pour bénéficier des fonctionnalités JavaScript locales (notamment les requêtes à l’API), il est recommandé d’utiliser une extension comme **Live Server** ou d’héberger les fichiers sur un petit serveur local.

### Backend

Depuis le dossier `Backend`, installez les dépendances puis lancez le serveur :

```bash
cd OpenClassrooms-SophieBluel-P6/Backend
npm install
npm start
```

Le serveur écoute par défaut sur `http://localhost:5678`. Les routes principales sont :

- `GET /api/works` : liste des projets.
- `GET /api/categories` : liste des catégories.
- `POST /api/user/login` : authentification (retourne un token).
- `POST /api/works` (authentifié) : ajout d’un projet avec upload d’image.
- `DELETE /api/works/:id` (authentifié) : suppression d’un projet.

La documentation Swagger est disponible à `http://localhost:5678/api-docs`.

## Licence

Projet pédagogique destiné à l’apprentissage. Utilisation libre dans un cadre éducatif.
