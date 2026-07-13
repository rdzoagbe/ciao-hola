# Daily Talk IT·ES — PWA installable (GitHub Pages)

App web installable pour apprendre l'italien et l'espagnol : dialogues hors-ligne,
mode jeu de rôle, audio, série de jours. Aucun serveur, aucune donnée envoyée.

## Déploiement (5 minutes)

Option A — nouveau dépôt :
1. Crée un dépôt GitHub public, ex. `daily-talk`
2. Pousse ces 5 fichiers à la racine :
   index.html · manifest.webmanifest · sw.js · icon-192.png · icon-512.png
3. Settings → Pages → Source : branche `main`, dossier `/ (root)` → Save
4. URL : https://rdzoagbe.github.io/daily-talk/

Option B — sous-dossier de ton site Pages existant :
copie les 5 fichiers dans un dossier `daily-talk/` de ton dépôt Pages.
Tous les chemins sont relatifs (`./`), donc ça fonctionne en sous-dossier.

## Installation sur Android
1. Ouvre l'URL dans Chrome sur ton téléphone
2. Une bannière « Installer l'application » apparaît (ou menu ⋮ → Installer l'application)
3. L'app s'installe : icône, plein écran, splash screen — et fonctionne ensuite
   100 % hors-ligne (service worker).

## Rappel quotidien — limite honnête
Une PWA ne peut pas déclencher de notification quand elle est fermée
(l'API « Notification Triggers » a été abandonnée par Chrome ; le Push nécessite un serveur).
Le rappel intégré fonctionne app ouverte. Pour un rappel fiable à 100 % :
Horloge Google → alarme quotidienne, ou événement récurrent Google Agenda.

## Voix hors-ligne
Paramètres Android → Synthèse vocale → Google TTS → télécharger Italiano et Español.

## Mise à jour du contenu
Modifie `DIALOGUES` dans index.html, pousse, puis dans sw.js incrémente
`CACHE = "dailytalk-v2"` pour forcer le rafraîchissement du cache chez les clients.
