# project-template

Base de démarrage de mes projets : instructions pour Claude, hook de commit et Dependabot.

## Contenu

| Fichier | Rôle |
|---|---|
| `CLAUDE.md` | Règles de travail pour Claude Code (commits, branches, style, tests, sécurité). Remplir les emplacements `<...>`. |
| `.githooks/commit-msg` | Refuse un message qui ne suit pas Conventional Commits. |
| `.github/dependabot.yml` | Mises à jour groupées `minor-and-patch`. Décommenter l'écosystème du projet. |
| `.gitignore` | Base minimale (`.env`, `node_modules/`, `.DS_Store`). |

## Nouveau projet

Les étapes dans l'ordre. Remplace `mon-projet` (et `G1TS23` si besoin).

### 1. Créer le repo depuis le template

```bash
gh repo create mon-projet --template G1TS23/project-template --private --clone
cd mon-projet
```

### 2. Activer le hook de commit

Projet Node : ajouter le script `prepare` dans `package.json`, le hook s'active alors à chaque `npm install` (et pour les sessions cloud).

```json
"prepare": "git config core.hooksPath .githooks || true"
```

Autre stack : une fois après le clone.

```bash
git config core.hooksPath .githooks
```

### 3. Remplir `CLAUDE.md`

- Titre et description du projet.
- Section « Stack et commandes » : stack, installation, dev, tests, lint, build. Ce sont les commandes que Claude lancera avant de considérer une tâche terminée.
- Section « Langue » : garde le défaut (code et commits en anglais, doc en français), ou remplace-la par « suis la langue déjà utilisée dans ce projet » (le commentaire HTML en dessous donne la formule). Supprime ensuite le commentaire.
- Ajoute une section « Spécificités du projet » si besoin (architecture, règles métier, fichiers à ne pas toucher).
- Retire les outils qui ne s'appliquent pas dans « Stack et outillage ».
- Vérifie qu'il ne reste aucun `<...>` : `grep -n '<' CLAUDE.md`.

### 4. Garder le bon écosystème Dependabot

Dans `.github/dependabot.yml`, décommenter `npm`, `cargo` ou `pip` selon le projet et supprimer les autres. `github-actions` reste. Si le projet n'a pas de CI, supprime aussi cette entrée.

### 5. Régler le repo GitHub

```bash
gh api -X PATCH repos/G1TS23/mon-projet \
  -F allow_merge_commit=false -F allow_squash_merge=true -F allow_rebase_merge=true \
  -F delete_branch_on_merge=true
```

Voir aussi la section « À régler dans GitHub » plus bas pour la protection de `main`.

### 6. Premier commit et suite

Le premier commit peut aller sur `main` (il n'y a pas encore de branche de base). Tout le reste passe par une branche et une PR.

```bash
git add -A
git commit -m "chore: initial project setup"
git push -u origin main
git switch -c feat/ma-premiere-fonctionnalite
```

## Projet existant

Copier `CLAUDE.md`, `.githooks/` et `.github/dependabot.yml`, adapter le bloc « Langue » à la langue déjà utilisée dans le projet, puis activer le hook.

## À régler dans GitHub

- Settings → General → Pull Requests : autoriser seulement squash et rebase (historique linéaire).
- Settings → General → Pull Requests : cocher « Automatically delete head branches » (ou `gh api -X PATCH repos/<owner>/<repo> -F delete_branch_on_merge=true`).
- Protéger `main` (PR obligatoire). Nécessite un repo public ou GitHub Pro.

Ces réglages ne sont pas hérités du template : à refaire pour chaque nouveau repo. La suppression automatique ne touche pas les branches locales (`git fetch --prune`, puis `git branch -D <branche>`).
