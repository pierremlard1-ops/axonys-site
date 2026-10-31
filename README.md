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

## Mise en ligne (VPS Hostinger, Docker + Traefik)

Le site tourne sur le même VPS que vIA Pyrénées, dans un conteneur `nginx:alpine` nommé `axonys-site`. Traefik (déjà en place) oriente coachaxonys.fr vers ce conteneur et gère le certificat HTTPS.

- `/docker/axonys-site/site` : clone de ce dépôt, mis à jour par `git pull` toutes les 5 minutes (crontab root)
- `/docker/axonys-site/docker-compose.yml` et `nginx.conf` : copies de `deploy/`

Après une modification de `deploy/nginx.conf`, recopier le fichier et relancer : `cd /docker/axonys-site && cp site/deploy/nginx.conf . && docker compose restart`.

Le fichier `.htaccess` ne sert que pour un hébergement Apache/LiteSpeed ; il est ignoré par Nginx.

## Modifier le site

Modifier le texte directement dans `index.html`, puis pousser sur `main`.
