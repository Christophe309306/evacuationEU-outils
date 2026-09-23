# Dimensionnement des évacuations d'eaux usées

Outil de pré-dimensionnement par tronçons cumulés, basé sur NBN EN 12056-1/-2.
Application web autonome (aucune dépendance serveur), installable comme une app (PWA).

## Utilisation locale
Ouvrez simplement `index.html` dans un navigateur. Le service worker (installation/hors-ligne) ne s'active qu'en HTTPS — voir ci-dessous pour l'activer pleinement.

## Héberger via GitHub Pages (recommandé)
1. Créez un dépôt GitHub et déposez-y tous les fichiers de ce dossier (`index.html`, `manifest.json`, `sw.js`, les icônes, ce `README.md`) à la racine.
2. Dans le dépôt : **Settings → Pages → Source : Deploy from a branch**, branche `main`, dossier `/ (root)`.
3. Après quelques minutes, l'outil est accessible à `https://<votre-utilisateur>.github.io/<nom-du-depot>/`.
4. Ouvrez cette adresse dans Chrome/Edge (ordinateur) ou Chrome (Android) : une icône d'installation apparaît dans la barre d'adresse ou le menu ⋮. Sur iPhone/iPad (Safari) : bouton Partager → « Sur l'écran d'accueil ».

## Mettre à jour l'outil
Remplacez `index.html` (et les autres fichiers modifiés) dans le dépôt, puis poussez (`git add`, `git commit`, `git push`). GitHub Pages republie automatiquement en 1 à 2 minutes. Les personnes ayant déjà installé l'app reçoivent la mise à jour au prochain lancement (le service worker rafraîchit le cache).

## Structure des fichiers
- `index.html` — l'outil complet (interface + calculs, tout en un seul fichier)
- `manifest.json` — métadonnées de l'app installable (nom, icônes, couleurs)
- `sw.js` — service worker (mise en cache pour le fonctionnement hors ligne)
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — icônes de l'app
