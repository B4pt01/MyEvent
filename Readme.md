# 🎉 MyEvent - Plateforme de Gestion d'Événements

## 📚 Description

**MyEvent** est une plateforme web de gestion d’événements permettant aux utilisateurs de :

- Créer un compte ou se connecter via Discord.
- Parcourir et consulter les événements disponibles.
- S'inscrire à des événements **en solo** ou **en équipe**.
- Consulter les détails, les récompenses et un **calendrier interactif** connecté à la base de données.

Le projet est structuré avec une **architecture MVC** côté backend et une **application React** côté frontend, le tout conteneurisé via **Docker**.

---

## ⚙️ Technologies utilisées

### 🐳 Docker

- Isolation des services : frontend, backend, base de données.
- `docker-compose` pour l'orchestration.

### 🧠 Backend

- **Node.js** + **Express.js** (architecture MVC)
- **PostgreSQL** (base de données relationnelle)
- **Prisma** (ORM)
- **Passport.js** + **passport-discord** pour l'auth
- API REST sécurisée

### 💻 Frontend

- **React.js** (avec Vite)
- **React Router DOM** pour la navigation
- **Tailwind CSS** pour le design global
- CSS par page pour des styles modulaires

---

## 🗂 Arborescence du projet

```bash
APP/
│
├── docker/ # Fichiers Docker (Dockerfile, .env, etc.)
│
├── backend/ # Application backend (Node.js + Express + MVC)
│ ├── controllers/ # Logique métier
│ ├── models/ # Modèles Prisma (User, Event, Team, etc.)
│ ├── routes/ # Définition des routes
│ ├── middlewares/ # Auth, validation, erreurs
│ ├── services/ # Intégration API externes (Discord OAuth)
│ ├── prisma/ # Schéma + seed + migration
│ ├── utils/ # Fonctions utilitaires
│ └── server.js # Point d’entrée du serveur
│
├── frontend/ # Application frontend React
│ ├── public/
│ ├── src/
│ │ ├── assets/
│ │ ├── components/ # Composants réutilisables
│ │ ├── pages/ # Home, Login, Event, etc.
│ │ ├── styles/ # common.css, home.css, event.css, etc.
│ │ ├── App.jsx
│ │ └── main.jsx
│ └── vite.config.js
│
├── database/ # Init / scripts SQL / backup
│
├── docker-compose.yml # Configuration multi-conteneur
├── .env # Variables d’environnement
└── README.md
```

---

## 🧩 Fonctionnalités clés

### Accueil

- Header avec image de fond + titre central : `🎉 MyEvent 🎉`
- Liste de **10 événements** sous forme de cartes (3 par ligne)
- Chaque carte mène à la page dédiée de l'événement

### Page Événement

- **Calendrier dynamique** connecté à la BDD
- **Description** et **récompenses**
- **Formulaire d’inscription** :
  - Solo : simple validation
  - Équipe : saisie des membres + nom

### Authentification

- Compte utilisateur classique (email/mot de passe)
- Authentification via **Discord OAuth2**

---

## 🚧 Étapes de développement

### 1. Initialisation du projet

- [x] Définir la stack (Node.js, React, Docker, PostgreSQL)
- [ ] Mettre en place le `docker-compose.yml`
- [ ] Créer la structure backend MVC
- [ ] Initialiser le projet React avec Tailwind

### 2. Backend

- [ ] Créer les modèles Prisma (`User`, `Event`, `Team`, `Registration`)
- [ ] Mettre en place l’auth (classique + Discord)
- [ ] Créer les routes API : `GET /events`, `POST /register`, etc.
- [ ] Connecter PostgreSQL via Prisma

### 3. Frontend

- [ ] Intégrer les routes React
- [ ] Créer les pages :
  - Accueil
  - Détail événement
  - Login/Register
- [ ] Intégrer les formulaires d’inscription
- [ ] Styliser avec Tailwind + fichiers CSS par page

### 4. Tests & finalisation

- [ ] Tester les scénarios d’inscription solo/équipe
- [ ] Vérifier le calendrier dynamique
- [ ] Vérifier la persistance et l’authentification

---

## ▶️ Lancer le projet

### 1. Cloner le dépôt

```bash
git clone [https://github.com/B4pt_01/MyEvent.git](https://github.com/B4pt01/MyEvent.git)
cd MyEvent
```

### 2. Lancer les conteneurs Docker

```bash
docker-compose up --build
```

### 3. Accéder aux services

Frontend : http://localhost:3000

Backend : http://localhost:5000/api

PostgreSQL : localhost:5432

## ✅ À venir

Panel admin pour gérer les événements

Gestion des équipes avancée

Système de notifications/email

## 📬 Contact

Projet développé par [B4pt_02]
📧 Contact : [bat.vauthier@gmail.com]
