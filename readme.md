# 🐾 Brief Projet Backend – Patte & Cie

## Base de données Neon + API Express.js (option TypeScript) + Déploiement Render

**Durée : 10 jours – Travail en duo**

---

## 🎯 Objectif général

Ce projet constitue la suite logique du prototype Front « Carnet de santé animal ».  
Vous allez construire un backend complet, connecté à une base de données en ligne, et exploitable par les projets Front réalisés par d’autres apprenants.  
Vous relierez ensuite votre API à deux projets Front réalisés par vos camarades pour valider l’intégration croisée.

Objectifs :

- Finaliser la modélisation : **MLD → MPD**
- Implémenter une base **PostgreSQL** hébergée sur **Neon.tech**
- Écrire l’ensemble des scripts SQL nécessaires (création, contraintes, jeu de données)
- Développer une **API REST** avec **Express.js** (JavaScript ou TypeScript)
- Connecter l’API à la base de données distante
- Déployer l’API sur **Render**
- Fournir une documentation claire permettant son intégration Front

---

# 🐱 Contexte

La clinique vétérinaire **Patte & Cie** dispose désormais de maquettes et de prototypes Front.  
Mais les données actuelles reposent sur des fichiers JSON statiques…

> “Nous voulons un vrai backend, une vraie base de données, et une API stable accessible partout !”

Votre mission : créer le **carnet de santé numérique backend**.

---

# 📦 Livrables attendus

## 1. 🧱 Modélisation (MLD & MPD)

### ✔ MLD – Modèle Logique de Données

- Conversion fidèle du MCD du projet précédent
- Normalisation (jusqu’en 3FN, troisième forme normale)
- Types et attributs pertinents

### ✔ MPD – Modèle Physique PostgreSQL

- Types SQL adaptés (UUID recommandé)
- Contraintes :
  - Clés primaires / étrangères
  - UNIQUE
  - CHECK
  - Index si nécessaires

📁 Fichiers attendus dans `/database` :

- `mld.pdf`
- `mpd.pdf`

---

## 2. 🗄️ Script SQL complet

Dans `/database/script.sql` :

- Création de la base et des tables
- Contraintes PK / FK / UNIQUE
- Jeu de données d’exemple (INSERT)
- Script exécutable tel quel sur Neon

---

## 3. 🐘 Base de données sur Neon.tech

Chaque duo doit :

- Créer un projet Neon
- Récupérer la `DATABASE_URL`
- Importer son script SQL
- Configurer la connexion dans l’API via `.env`

---

## 4. ⚙️ Développement de l’API Express.js

### Stack obligatoire :

- Node.js + Express.js
- PostgreSQL (Neon)
- JavaScript ou **TypeScript (valorisé)**
- ORM possible : **Prisma** (recommandé)

### Architecture recommandée :

- `src/app.(js|ts)` pour la configuration Express
- `src/routes/` pour déclarer les routes REST (ou un système automatisé type [`express-file-routing`](https://www.npmjs.com/package/express-file-routing/v/2.0.0))
- `src/controllers/` pour gérer les entrées/sorties HTTP
- `src/services/` pour la logique métier
- `src/repositories/` ou accès ORM (Prisma) pour la base
- `prisma/schema.prisma` (si Prisma) ou migrations SQL versionnées
- Tests dans `tests/` (Jest ou Vitest) et scripts npm associés

### Fonctionnalités attendues

- Gestion des animaux, propriétaires, rendez-vous, vétérinaires, traitements, vaccins, observations
- CRUD complet sécurisé (validation, codes de statut HTTP cohérents)
- Filtrage/pagination sur les listes critiques
- Gestion des erreurs centralisée (middlewares)
- Authentification simple (token, clé API ou autre solution validée) si besoin selon les données sensibles

---

## 5. 🚀 Déploiement Render

- Créer un service Web Render relié à votre repo
- Configurer les variables d’environnement (`DATABASE_URL`, `PORT`, `NODE_ENV`, etc.)
- Déployer la branche principale et vérifier les logs
- Fournir l’URL publique fonctionnelle

---

## 6. 🔗 Intégration avec deux projets Front

- Choisir deux projets Front réalisés par d’autres apprenants (liste fournie par la promo)
- Partager votre documentation API et coordonner les champs attendus
- Réaliser au moins une démonstration de bout en bout par projet (capture vidéo ou courte présentation)
- Documenter les ajustements nécessaires côté Front (issues, PR ou notes)

---

## 7. ✅ Qualité & Tests

- Linters/formatters configurés (`eslint`, `prettier`, etc.)
- Tests unitaires et/ou d’intégration sur les endpoints critiques
- Script `npm test` ou `npm run test:watch` fonctionnel
- Couverture minimale attendue : endpoints principaux et services métiers sensibles
- Respect des bonnes pratiques Git (issues, branches, PR regroupant les features)

---

## 8. 📝 Documentation & Handoff

- README racine détaillé (setup local, scripts, env, stratégie de déploiement)
- Documentation API (Swagger/OpenAPI, Postman Collection ou Markdown clair)
- Section “Intégration Front” expliquant comment consommer l’API (routes, exemples de payload, codes de statut)
- Changelog ou journal de version simple

---

## 9. 🤝 Organisation & Planning en duo

- Répartition des rôles (ex. lead backend / lead data, puis rotation)
- Daily courte (15 min) pour suivre l’avancement
- Kanban ou board Notion/Trello partagé avec les tâches
- Point de synchronisation avec les porteurs des projets Front à J+3 et J+7
- Rétrospective finale (forces, axes d’amélioration, feedback croisé)

---

Bon courage, la clinique compte sur vous pour donner vie au carnet de santé connecté de Patte & Cie !
