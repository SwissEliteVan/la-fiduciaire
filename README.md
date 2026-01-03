# La Fiduciaire — Application Node.js

Ce dépôt contient une application Node.js (Express + EJS) qui restitue l'ensemble des contenus de La Fiduciaire à partir de fichiers Markdown avec frontmatter.

## Structure
- `content/` : pages en Markdown (slug, titres et descriptions en frontmatter).
- `src/` : serveur Express, chargement du contenu et vues EJS.
- `public/` : assets statiques (CSS).

## Démarrage
1. Installer les dépendances : `npm install`
2. Lancer le serveur en développement : `npm run dev`
3. Lancer en production : `npm start`

L'application démarre sur http://localhost:3000 par défaut.

## Déploiement sur Hostinger
- Créer une application Node.js et pointer la racine vers ce dépôt.
- Définir la commande de démarrage sur `npm start` (le point d'entrée `index.js` démarre automatiquement le serveur Express).
- Hostinger fournit la variable d'environnement `PORT` : le serveur l'utilise automatiquement et écoute sur `0.0.0.0` pour être joignable par le proxy.
- Optionnel : définir `HOST` si vous devez restreindre l'écoute réseau.

## Navigation
Les slugs définis dans le frontmatter sont utilisés pour générer les routes :
- `/` (accueil)
- `/services/`
- `/guides/`
- `/tarifs/`
- `/a-propos/`
- `/contact/`
- `/faq/`

Une route `/health` renvoie un JSON simple pour vérifier que le service répond.
