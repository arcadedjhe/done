# Done — vaporisateur de tâches

Une to-do list minimaliste, installable depuis Chrome, qui fonctionne hors-ligne.
Les données restent dans ton navigateur (aucun serveur, aucun compte).

## Règles

- **Tâche** : titre, échéance (calendrier), prioritaire oui/non, périodique oui/non (« tous les N jours »).
- **Priorité automatique** : quand il reste moins de 5 % du temps prévu (de la création à l'échéance), la tâche devient prioritaire.
- **Retard** : l'échéance court jusqu'à la fin du jour choisi.
  - 1er jour de retard : tâche **jaune**, en tête de liste.
  - À partir du 2e jour : tâche **rouge**, grande et pulsante, tout en haut.
- **Périodique** : en validant la tâche, la prochaine occurrence se recrée (échéance + N jours ; si tu étais en retard, N jours à partir d'aujourd'hui).
- **Aujourd'hui** : retards, prioritaires, et échéances dans les 2 jours. Le reste est dans « Plus tard ».
- **Pas d'historique** : une tâche validée disparaît.
- **Sauvegarde** : menu « ⋯ » pour exporter / importer un fichier JSON.

## Déployer sur GitHub Pages

1. Crée un dépôt GitHub (par exemple `done`), public.
2. Dépose à la racine : `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`, `README.md`.
3. Dépôt → **Settings** → **Pages** → *Build and deployment* : source **Deploy from a branch**, branche `main`, dossier `/ (root)` → **Save**.
4. Après une minute, l'appli est disponible sur `https://TON-PSEUDO.github.io/done/`.

## Installer avec Chrome

- **PC** : ouvre l'adresse, clique sur l'icône d'installation dans la barre d'adresse (ou menu ⋮ → *Caster, enregistrer et partager* → *Installer la page en tant qu'application*).
- **Android** : menu ⋮ → *Installer l'application*.

## Mettre à jour

Remplace `index.html` dans le dépôt. Pour forcer le renouvellement du cache hors-ligne, change aussi la valeur `CACHE` dans `sw.js` (`done-v2`, etc.).

## Réglages

En haut du script de `index.html` :

- `PRIO_RATIO` : 0.05 (seuil des 5 %)
- `SOON_DAYS` : 2 (échéances affichées dans « Aujourd'hui »)
