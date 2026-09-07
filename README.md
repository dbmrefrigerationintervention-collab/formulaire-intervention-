# Fiche d'intervention — DNM Réfrigération / FOOD Equipment

Outil web pour remplir, enregistrer et envoyer les fiches d'intervention,
avec base clients partagée et accessible depuis n'importe quel appareil
(téléphone, tablette, ordinateur) via un hébergement gratuit.

## Déploiement (à faire une seule fois)

### 1. Créer la base de données (Supabase)

1. Créer un compte gratuit sur [supabase.com](https://supabase.com) et un nouveau projet.
2. Dans le projet, aller dans **SQL Editor** > **New query**, coller le contenu
   de `supabase_schema.sql` fourni dans ce dossier, puis **Run**.
3. Aller dans **Project Settings > API** et noter :
   - **Project URL**
   - **anon public key**

### 2. Configurer le site

1. Ouvrir `index.html`.
2. Remplacer, tout en haut du script :
   ```js
   const SUPABASE_URL = "VOTRE_SUPABASE_URL";
   const SUPABASE_ANON_KEY = "VOTRE_SUPABASE_ANON_KEY";
   ```
   par les valeurs copiées à l'étape précédente.

### 3. Mettre le code sur GitHub

1. Créer un nouveau dépôt (public ou privé) sur [github.com](https://github.com).
2. Y déposer `index.html` (et ce `README.md`) — soit par glisser-déposer sur
   la page du dépôt, soit via `git push`.

### 4. Déployer sur Vercel

1. Créer un compte gratuit sur [vercel.com](https://vercel.com) (connexion possible via GitHub).
2. **Add New… > Project**, importer le dépôt GitHub créé à l'étape précédente.
3. Aucune configuration de build n'est nécessaire (site statique) : cliquer sur **Deploy**.
4. Vercel fournit une adresse du type `https://votre-projet.vercel.app`,
   accessible depuis n'importe quel appareil, à ajouter en raccourci sur
   l'écran d'accueil des téléphones/tablettes de l'équipe.

Toute modification poussée sur GitHub (`git push`) redéploie automatiquement
le site sur Vercel.

## Envoi automatique par e-mail

Voir `Code.gs` et le guide d'installation fourni séparément — l'adresse
utilisée est `dbmrefrigerationintervention@gmail.com`. Ce fonctionnement est
indépendant de l'hébergement ci-dessus.

## Sécurité — à savoir

Ce site n'a pas de système de compte utilisateur : toute personne qui connaît
l'adresse du site déployé peut consulter et modifier les fiches et la base
clients (comme un lien partagé sans mot de passe). Cela convient à un usage
en équipe restreinte. Si un accès protégé devient nécessaire, on peut ajouter
une authentification Supabase par la suite.
