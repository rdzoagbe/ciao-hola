# Ciao·Hola — PWA installable (GitHub Pages)

App web installable pour apprendre l'italien et l'espagnol : dialogues hors-ligne,
mode jeu de rôle, mode « Écouter & répondre » (l'app joue les répliques du
partenaire, tu réponds au micro et elle vérifie), audio, série de jours.
Aucun serveur, aucune donnée envoyée.

## Déploiement (5 minutes)

Les 5 fichiers sont à la racine de ce dépôt :
index.html · manifest.webmanifest · sw.js · icon-192.png · icon-512.png

1. Settings → Pages → Source : branche `main`, dossier `/ (root)` → Save
2. URL : https://rdzoagbe.github.io/ciao-hola/

Alternative — sous-dossier de ton site Pages existant :
copie les 5 fichiers dans un dossier `ciao-hola/` de ton dépôt Pages.
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

## Mode « Écouter & répondre » — limite honnête
La vérification au micro utilise la reconnaissance vocale du navigateur
(Chrome Android : nécessite internet et l'autorisation micro). Sans elle,
le mode fonctionne quand même : dis ta réplique, puis affiche la réponse
pour comparer toi-même.

## Mise à jour du contenu
Modifie `DIALOGUES` dans index.html, pousse, puis dans sw.js incrémente
`CACHE = "ciaohola-v4"` (numéro suivant) pour forcer le rafraîchissement
du cache chez les clients.
