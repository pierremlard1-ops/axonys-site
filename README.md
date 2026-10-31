# Axonys — site internet

Site statique (HTML/CSS, sans base de données ni compilation) d'Axonys, Pierre-Emmanuel Lardin : https://coachaxonys.fr

## Contenu

- `index.html` — page d'accueil
- `mentions-legales.html` — mentions légales et politique de confidentialité
- `404.html` — page d'erreur
- `assets/` — feuille de style, polices, portrait, logo Osez l'IA, favicon, image de partage
- `robots.txt`, `sitemap.xml` — référencement
- `.htaccess` — HTTPS forcé, adresse sans www, cache, en-têtes de sécurité (hébergement web Hostinger)

Le formulaire de contact ouvre la messagerie du visiteur avec un email prérempli vers coachaxonys@gmail.com : aucune donnée n'est envoyée à un serveur.

Les polices (Space Grotesk, Manrope, JetBrains Mono) sont hébergées dans `assets/fonts/` sous licence SIL Open Font License : le site n'appelle aucun service tiers et ne dépose aucun cookie.

## Mise en ligne sur Hostinger (hébergement web)

1. hPanel → **Sites web** → **Gérer** sur coachaxonys.fr → **Avancé** → **Git**.
2. **Connecter avec GitHub**, autoriser l'application Hostinger sur ce dépôt.
3. Choisir ce dépôt, branche `main`, dossier `public_html`, puis **Déployer**.
4. Chaque `git push` sur `main` redéploie automatiquement le site.

Le déploiement remplace le contenu du dossier cible.

## Modifier le site

Modifier le texte directement dans `index.html`, puis pousser sur `main`.
