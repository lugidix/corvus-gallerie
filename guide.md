# Guide complet — Déployer un site statique sur GitHub Pages

> Rédigé pour le projet CORVUS × 13, valable pour n'importe quel site statique
> (HTML/CSS/JS, sans build). Chaque étape a été réellement exécutée sur ce dépôt.

---

## Prérequis (une seule fois)

1. **Un compte GitHub** — gratuit, sur [github.com](https://github.com).
2. **Git installé** — vérifier avec `git --version` (télécharger sur git-scm.com sinon).
3. C'est tout. GitHub Pages est gratuit pour les dépôts **publics**.

## Étape 0 — Préparer le projet

- Un fichier **`index.html` à la racine** du dossier : c'est la page d'accueil que
  GitHub Pages sert automatiquement.
- Des **chemins relatifs** partout (`css/style.css`, `pages/x.html`) — jamais de
  chemins absolus type `C:/Users/...`.
- Optionnel mais recommandé : un fichier vide **`.nojekyll`** à la racine, pour que
  GitHub serve les fichiers tels quels sans passer par son générateur Jekyll.

## Étape A — Créer le dépôt sur github.com

1. Se connecter, cliquer sur le **+** en haut à droite → **New repository**.
2. **Repository name** : le nom du projet (il apparaîtra dans l'URL finale :
   `nom-du-repo` → `https://pseudo.github.io/nom-du-repo/`).
3. Visibilité : **Public** (obligatoire pour Pages sur le forfait gratuit).
4. Ne pas cocher « Add a README » si le dossier local existe déjà (évite un conflit
   au premier push). Cocher si on part de zéro côté web.
5. **Create repository**. Copier l'URL proposée :
   `https://github.com/pseudo/nom-du-repo.git`

## Étape B — Relier le dossier local et pousser (terminal, dans le dossier du site)

```bash
# 1. Se placer dans le dossier du site
cd chemin/vers/mon-site

# 2. Transformer le dossier en dépôt Git (si ce n'est pas déjà fait)
git init -b main

# 3. Identifier ses commits (une seule fois par machine)
git config --global user.name "Mon Pseudo"
git config --global user.email "mon.email@exemple.com"

# 4. Enregistrer tous les fichiers
git add -A
git commit -m "Première version du site"

# 5. Relier au dépôt GitHub et pousser
git remote add origin https://github.com/pseudo/nom-du-repo.git
git push -u origin main
```

- Au **premier push**, une fenêtre GitHub s'ouvre pour se connecter (Navigateur) :
  valider une fois, c'est mémorisé.
- Si le push est refusé parce que le dépôt en ligne contient déjà un README :
  `git pull --rebase origin main` puis repousser.
- Si la branche s'appelle `master` : `git branch -M main` avant de pousser.

## Étape C — Activer GitHub Pages (sur la page du dépôt)

1. Onglet **Settings** (roue dentée, en haut).
2. Menu de gauche → **Pages** (section « Code, planning, and automation »).
3. **Build and deployment → Source** : choisir **Deploy from a branch**.
4. **Branch** : `main` et dossier **`/ (root)`** → bouton **Save**.
5. **Laisser le champ « Custom domain » VIDE** (si quelque chose y traîne : bouton
   *Remove*). Un domaine custom exige d'en posséder un et de configurer son DNS.
6. Message vert « GitHub Pages source saved. » = enregistré.

## Étape D — Attendre le build et vérifier

1. Onglet **Actions** : une exécution **« pages build and deployment »** apparaît ;
   attendre la coche verte (1 à 2 minutes).
2. Ouvrir `https://pseudo.github.io/nom-du-repo/`.
3. Si une ancienne version s'affiche : **Ctrl+Shift+R** (rechargement sans cache).
4. Tester chaque page interne depuis le site en ligne.

## Étape E — Publier chaque mise à jour (le quotidien)

```bash
cd chemin/vers/mon-site
git add -A
git commit -m "Description de la modification"
git push
```

Le site se reconstruit tout seul en ~1 minute. Rien d'autre à faire.

## Dépannage — les erreurs classiques

| Symptôme | Cause | Remède |
|---|---|---|
| 404 sur l'URL du site | Build en cours → attendre 2 min | Onglet Actions, vérifier la coche verte |
| 404 permanent | Dépôt **privé** (Pages gratuit = public uniquement) | Settings → General → Danger Zone → Change visibility → Public |
| 404 permanent | Pas de `index.html` à la racine | Ajouter et pousser |
| Le build ne démarre jamais | Un « Custom domain » invalide enregistré dans Settings → Pages | Le vider (*Remove*), puis re-pousser pour déclencher |
| `failed to push some refs` | Le dépôt en ligne a des commits absents en local | `git pull --rebase origin main` puis `git push` |
| Site affiche une vieille version | Cache navigateur | Ctrl+Shift+R |
| Pages en erreur « Jekyll » | Traitement Jekyll inutile | Ajouter un fichier vide `.nojekyll` |
| CSS/images absentes en ligne | Chemins absolus ou casse différente (GitHub est sensible à la casse) | Chemins relatifs, respecter la casse des noms |

## Variante 100 % web (sans terminal)

1. Créer le dépôt (étape A), puis sur la page du dépôt vide :
   **« uploading an existing file »** → glisser-déposer tous les fichiers → **Commit changes**.
2. Activer Pages (étape C). C'est tout — mais chaque mise à jour repasse par un
   glisser-déposer manuel, et au-delà de ~100 fichiers c'est pénible.

## Aller plus loin

- **Domaine personnalisé** : posséder `mondomaine.fr`, le saisir dans Settings → Pages,
  créer chez le registrar un enregistrement CNAME vers `pseudo.github.io`, attendre le
  DNS, cocher *Enforce HTTPS*.
- **GitHub Actions** : un workflow `.github/workflows/deploy.yml` peut remplacer
  « Deploy from a branch » pour minifier, optimiser les images ou builder avant déploiement.
- **Site par pseudo** : un dépôt nommé `pseudo.github.io` sert directement
  `https://pseudo.github.io/` à la racine (un seul par compte).
