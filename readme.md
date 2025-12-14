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
Mais les données actuelles reposent sur des fichiers JSON statiques et aucune relance automatique n’est faite pour les vaccins à renouveler…

> “Nous voulons un vrai backend, une vraie base de données, et une API stable accessible partout !”

Votre mission : créer le **carnet de santé numérique backend**.

---

# 📦 Livrables attendus

## 1. 🧱 Modélisation (MLD & MPD)

### ✔ MLD – Modèle Logique de Données

- Chaque apprenant arrive avec son MCD déjà conçu : le duo échange et fusionne les meilleures idées pour produire un modèle commun
- Conversion fidèle du MCD du projet précédent
- Normalisation
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
- `src/jobs/` pour les tâches planifiées (ex. [`node-cron`](https://www.npmjs.com/package/node-cron) ou Render Cron Jobs) dédiées aux relances vaccins

### Fonctionnalités attendues

- Gestion des animaux, propriétaires, rendez-vous, vétérinaires, traitements, vaccins, observations
- CRUD complet sécurisé (validation, codes de statut HTTP cohérents)
- Filtrage/pagination sur les listes critiques
- Gestion des erreurs centralisée (middlewares)
- Authentification simple (token, clé API ou autre solution validée) si besoin selon les données sensibles
- Tâche planifiée (cron ou équivalent) pour préparer et envoyer les relances de vaccins à l’approche des échéances (email, notification ou webhook)

---

## 5. 🚀 Déploiement Render

- Créer un service Web Render relié à votre repo
- Configurer les variables d’environnement (`DATABASE_URL`, `PORT`, `NODE_ENV`, etc.)
- Déployer la branche principale et vérifier les logs
- Fournir l’URL publique fonctionnelle

---

## 6. 🔗 Intégration avec deux projets Front

- Deux projets Front réalisés par d’autres apprenants vous seront attribués aléatoirement
- Forker ou dupliquer ces fronts et intégrer vous-mêmes l’API (pas de coordination nécessaire avec l’équipe d’origine)
- Adapter les services/pages pour consommer votre backend et valider l’UX
- Documenter les ajustements réalisés côté Front (issues, PR ou notes) et fournir une démonstration de bout en bout

---

## 7. ✅ Qualité & Tests (BONUS)

- Linters/formatters configurés (`eslint`, `prettier`, etc.)
- Tests unitaires et/ou d’intégration sur les endpoints critiques
- Script `npm test` ou `npm run test:watch` fonctionnel
- Couverture minimale attendue : endpoints principaux et services métiers sensibles
- Respect des bonnes pratiques Git (issues, branches, PR regroupant les features)

---

## 8. 📝 Documentation

- README racine détaillé (setup local, scripts, env, stratégie de déploiement)
- Documentation API (Swagger/OpenAPI, Postman Collection ou Markdown clair)
- Section “Intégration Front” expliquant comment consommer l’API (routes, exemples de payload, codes de statut)
- Changelog ou journal de version simple

---

## 9. 🤝 Organisation & Planning en duo

- Daily courte (15 min) pour suivre l’avancement
- GitHub Projects détaillé (colonnes backlog → en cours → en revue → terminé) avec issues liées, estimations et checklists de sous-tâches
- Point de suivi interne (J+3 et J+7) sur l’avancement des deux intégrations Front prises en charge par l’équipe backend
- Rétrospective finale (forces, axes d’amélioration, feedback croisé)

---

Bon courage, la clinique compte sur vous pour donner vie au carnet de santé connecté de Patte & Cie !
