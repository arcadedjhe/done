# Done — vaporisateur de tâches

Une to-do list minimaliste, installable depuis Chrome, qui fonctionne hors-ligne.
Les données restent dans ton navigateur (aucun serveur, aucun compte).

## Règles

- **Tâche** : titre, échéance (calendrier), heure facultative (23:59 par défaut), prioritaire oui/non, périodique oui/non (« tous les N jours »).
- **Temps prévu** : de la création de la tâche à son échéance. La barre de progression indique la part de ce temps déjà écoulée.
- **Barre de progression**
  - Tâche courte (moins de 2 jours) ou moyenne (2 jours à 90 jours) : la barre apparaît quand il reste 10 % du temps.
  - Tâche longue (plus de 90 jours) : la barre apparaît dès 25 % du temps écoulé, avec des repères à 50 % et 75 %.
- **Couleurs (zen)** : 10 % restants → **jaune** ; 5 % restants → **rouge doux**.
- **Priorité automatique** : une tâche devient prioritaire dès qu'il reste 10 % du temps prévu.
- **Retard** : un seul niveau, **rouge plein** qui pulse, tout en haut de la liste, avec le temps de retard.
- **Périodique** : en validant la tâche, la prochaine occurrence se recrée (échéance + N jours ; si tu étais en retard, N jours à partir d'aujourd'hui) et le décompte repart à zéro.
- **Aujourd'hui** : retards, prioritaires, et échéances dans les 2 jours. Le reste est dans « Plus tard ».
- **Modifier l'échéance** : la date de création d'origine est conservée, la barre reflète donc le temps réellement écoulé.
- **Annulation** : après une validation ou une suppression, un bandeau « Annuler » reste affiché 10 secondes. Les 10 dernières tâches terminées ou supprimées restent aussi récupérables pendant 24 h dans le menu « ⋯ » (« Récupérer une tâche »), puis sont effacées automatiquement. Annuler une tâche périodique restaure son ancienne échéance.
- **Pas d'historique durable** : au-delà de 24 h, une tâche validée a disparu pour de bon.
- **Sauvegarde** : menu « ⋯ » pour exporter / importer un fichier JSON.

## Sous-tâches

- **Ajout** : depuis la carte (« + sous-tâche », champ à remplir puis Entrée) ou depuis le formulaire de la tâche (titre, date facultative, ↑ ↓ pour réordonner, × pour supprimer). Un seul niveau, 20 sous-tâches maximum.
- **Affichage** : la carte montre « 2/5 ». Toucher ce compteur déplie la liste, toucher le titre ouvre la modification. Les sous-tâches faites restent visibles, barrées, jusqu'à la validation de la tâche principale.
- **Mode « dans l'ordre »** : seule la prochaine étape peut être cochée, les suivantes sont grisées, et la carte indique « Prochaine : … ». Sans ce mode, les étapes se cochent dans n'importe quel ordre.
- **Temps** : une sous-tâche sans date suit celle de la tâche principale. Avec une date, son temps court du début de la tâche principale jusqu'à cette date, avec les mêmes seuils (10 % jaune, 5 % rouge, puis retard). Une date postérieure à l'échéance de la tâche est ramenée à cette échéance à l'enregistrement, avec un message.
- **L'urgence remonte** : si une étape non faite passe au jaune, au rouge ou en retard, la tâche principale prend la même couleur, devient prioritaire et nomme l'étape en cause.
- **Validation** : terminer une tâche qui a encore des sous-tâches ouvertes demande confirmation. Cocher la dernière sous-tâche ne ferme pas la tâche : c'est toi qui la termines.
- **Tâches périodiques** : à chaque nouvelle occurrence, les sous-tâches sont décochées et leurs dates décalées comme l'échéance.
- **Annulation** : restaure la tâche avec ses sous-tâches. L'export et l'import les conservent.

## Déployer sur GitHub Pages

1. Dépôt GitHub public (ici `done`).
2. Déposer à la **racine** : `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`, `README.md`. Les deux icônes sont indispensables à l'installation.
3. Dépôt → **Settings** → **Pages** → *Deploy from a branch* → `main` / `(root)`.
4. L'appli est disponible sur `https://TON-PSEUDO.github.io/done/`.

## Installer avec Chrome

- **PC** : icône d'installation dans la barre d'adresse, ou menu ⋮ → *Installer la page en tant qu'application*.
- **Android** : menu ⋮ → *Installer l'application*.

## Mettre à jour

Remplace les fichiers modifiés dans le dépôt. Pour forcer le renouvellement du cache hors-ligne, change la valeur `CACHE` dans `sw.js` (`done-v4`, etc.).

## Réglages

En haut du script de `index.html` : `YELLOW_AT` (0.90), `RED_AT` (0.95), `LONG_BAR_AT` (0.25), `SHORT_MAX` (2 jours), `LONG_MIN` (90 jours), `SOON_DAYS` (2).
