# Mini-brief projet SQL – Patte & Cie

Triggers, procédures stockées et requêtes SQL métier  
PostgreSQL – Titre Professionnel CDA

---

## Objectif pédagogique

Ce mini-projet a pour objectif de consolider votre maîtrise de PostgreSQL dans un contexte backend réaliste.

Vous travaillerez sur :

- la protection des règles métier au niveau de la base de données
- la distinction entre logique applicative et logique base
- l’écriture et la lecture de requêtes SQL métier
- la capacité à justifier des choix techniques

À l’issue de ce travail, vous devez être capable d’expliquer quand et pourquoi utiliser :

- un trigger
- une procédure stockée
- des requêtes SQL complexes

---

## Contexte métier

La clinique vétérinaire **Patte & Cie** dispose désormais d’un backend fonctionnel.

Certaines règles métier sont critiques, automatiques ou irréversibles et ne doivent pas dépendre uniquement de l’API.

Trois besoins ont été identifiés :

- calcul automatique des rappels de vaccination
- déclaration du décès d’un animal et gestion de ses impacts
- extraction de données métier via des requêtes SQL

---

## Livrables attendus

Un script SQL unique contenant :

- un trigger PostgreSQL
- une procédure stockée PostgreSQL
- les requêtes SQL demandées
- des commentaires expliquant les choix réalisés

Le script doit être exécutable directement dans la console PostgreSQL (Neon.tech).

---

## Partie 1 – Trigger : calcul automatique des rappels de vaccination

### Besoin métier

Lorsqu’une vaccination est enregistrée :

- la date de prochaine vaccination ne doit pas être saisie manuellement
- elle doit être calculée automatiquement à partir :
  - de la date d’administration
  - de la durée de validité du vaccin

La durée de validité est une propriété du vaccin, pas de l’acte de vaccination.

### Travail demandé

Mettre en place un trigger PostgreSQL qui :

- se déclenche lors de l’insertion d’une vaccination
- calcule automatiquement la date de prochaine vaccination
- garantit la cohérence des données

Contraintes :

- trigger BEFORE INSERT
- fonction en plpgsql
- SQL lisible et commenté
- un seul trigger maximum

---

## Partie 2 – Procédure stockée : déclaration du décès d’un animal

### Besoin métier

Lorsqu’un animal décède :

- son statut passe à **DÉCÉDÉ**
- la date de décès est enregistrée
- les visites en cours sont annulées ou clôturées
- les rappels de vaccination futurs sont désactivés

Cette action est critique, irréversible et doit être traitée de façon atomique.

### Travail demandé

Créer une procédure stockée PostgreSQL qui :

- prend en paramètre l’identifiant de l’animal et la date de décès
- vérifie que l’animal existe et n’est pas déjà décédé
- applique automatiquement toutes les conséquences métier
- empêche toute incohérence en cas d’erreur

Contraintes :

- procédure simple et lisible
- gestion des cas d’erreur
- une seule procédure maximum

---

## Partie 3 – Requêtes SQL métier

Vous devez écrire les requêtes SQL suivantes, exécutables directement sur la base PostgreSQL.

- Lister les animaux par date de naissance (du plus jeune au plus âgé)
- Afficher le nombre d’animaux par espèce
- Trouver tous les animaux d’un propriétaire donné
- Lister les vétérinaires et le nombre de visites réalisées
- Lister les animaux sans vaccination enregistrée
- Tester la procédure stockée de déclaration de décès

---

## Critères de réussite

- le trigger s’exécute automatiquement et correctement
- la procédure stockée applique toutes les règles métier attendues
- les requêtes SQL sont cohérentes et lisibles
- le SQL est commenté et compréhensible
- les choix techniques sont justifiables à l’oral

---

## Attendus pédagogiques (CDA)

À l’issue de ce mini-projet, vous devez être capable de :

- différencier trigger et procédure stockée
- justifier le placement d’une règle métier en base
- écrire des requêtes SQL exploitables
- expliquer vos choix techniques dans un contexte professionnel
