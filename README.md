# French-app-Demo

Banc d'essai de l'application client WoodMood en français.

**https://henri-dlgx.github.io/French-app-Demo/**

## À quoi sert ce dépôt

C'est ici qu'atterrissent les fonctionnalités en cours de validation. Le dépôt
de production [`WM_App-French`](https://github.com/Henri-dlgx/WM_App-French)
(servi sur **app.connectwoodmood.com**) ne reçoit que des versions stables.

Le flux est donc : *écrire et tester ici → porter dans `WM_App-French` une fois
la fonctionnalité validée sur un poêle.*

## Différences volontaires avec la production

Ce ne sont pas des oublis de migration — les reproduire à l'identique dans
`WM_App-French` serait une erreur :

| Différence | Raison |
|---|---|
| Pas de fichier `CNAME` | Un `CNAME` avec `app.connectwoodmood.com` détournerait le domaine des clients vers cette démo. GitHub n'autorise qu'un dépôt par domaine. |
| Clés `localStorage` suffixées `_demo` | `localStorage` est cloisonné par **origine**, pas par chemin : cette démo et la copie Pages de la production partagent `henri-dlgx.github.io`. Sans suffixe, tester ici écraserait le numéro de série, le mot de passe, la programmation et l'acceptation des CGU enregistrés là-bas. |
| `start_url` / `scope` relatifs (`./`) | La production est à la racine de son domaine, la démo est sous `/French-app-Demo/`. Un chemin absolu `/` installerait un raccourci vers une page 404. |
| Bandeau « BUILD DE DÉMONSTRATION », thème ardoise | Cette app pilote un vrai poêle. Il faut voir immédiatement qu'on n'est pas sur la version stable. |

## Numéro de série

Le poêle ciblé se choisit dans le panneau de connexion (numéro de série + mot
de passe) — rien n'est codé en dur. Pour tester sans toucher à un poêle client,
utiliser un numéro de série de banc.
