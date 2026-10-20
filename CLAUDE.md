# PEP

Rédaction des trois livrables du Projet d'Étude Professionnel (Mastère EADL, RNCP39765, EFREI) : rapports Mission 1, Mission 2 et PEP, plus la soutenance.

## Stack et commandes

- Stack : Markdown, conversion en PDF avec `pandoc` (non installé par défaut, à valider avant usage).
- Installer, dev, tests, lint : aucun.
- Build : `pandoc docs/mission-2/rapport.md -o build/EADL_Mission2_Nom_Prenom.pdf` (exemple, non testé).

Avant de considérer une tâche terminée, relis le texte avec `docs/modeles/checklist-grille.md`.

## Spécificités du projet

- Source de référence : l'Annexe 1 du PEP, résumée dans `docs/guide-livrables-pep.md`.
- Un dossier par mission dans `docs/` : `plan.md`, `rapport.md`, `annexes/`. Modèles dans `docs/modeles/`, sources dans `docs/sources/`, soutenance dans `docs/oral/`.
- N'invente jamais de fait sur l'entreprise, le projet ou les chiffres : laisse `<à compléter>`.
- Aucune donnée confidentielle d'entreprise dans le dépôt.
- Pas de code dans le corps des rapports (l'école le déconseille) : annexes seulement.

## Langue

- Tout est en **français** : documentation, messages de commit, descriptions de PR, noms de branches et réponses à l'utilisateur.
- Seuls les mots-clés techniques restent en anglais : types Conventional Commits (`docs`, `feat`…), préfixes de branche (`docs/`, `chore/`) et le trailer `Co-Authored-By`.

## Stack et outillage

- Versions de runtime épinglées (`.nvmrc`, `rust-toolchain.toml`, `.python-version`).
- Formatage et lint obligatoires avant commit :
  - JS/TS : Prettier + ESLint (`npm run format`, `npm run lint`)
  - Rust : `cargo fmt` + `cargo clippy -- -D warnings`
  - Python : Ruff (`ruff format`, `ruff check`)
- Dependabot activé, avec les mises à jour mineures/patch groupées (`minor-and-patch`).
- N'ajoute pas un outil de lint ou de format à un projet qui n'en a pas sans me le demander.

## Commits

Conventional Commits, un seul sujet par commit :

```
type(scope): description
```

- Types : `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.
- Description à l'impératif, en minuscules, sans point final, 72 caractères max.
- `scope` optionnel : le module ou dossier touché (`ci`, `hooks`, `auth`).
- Corps (si le changement n'est pas évident) : explique le **pourquoi**, ce qui a été vérifié et ce qui reste hors de portée. Ligne vide avant. Un changement trivial se contente d'une ligne.
- Issue liée : pied `Refs #123` (ou `Closes #123` si la PR la résout).
- Rupture de compatibilité : `!` après le type/scope et un pied `BREAKING CHANGE: ...`.
- Un commit = un changement logique. Ne mélange pas refactor et feature.
- Ne commite jamais de code qui ne passe pas les tests.
- Conserve le trailer `Co-Authored-By` ajouté pour Claude.
- Le format est vérifié par le hook `.githooks/commit-msg`. Si un commit est refusé, corrige le message, ne contourne jamais le hook (`--no-verify` interdit).

### Activer les hooks

Les hooks vivent dans `.githooks/` (versionnés) et s'activent automatiquement à l'installation :

```json
"prepare": "git config core.hooksPath .githooks || true"
```

Hors projet Node : `git config core.hooksPath .githooks` une fois après le clone.

## Git et branches

- Ne travaille **jamais** directement sur `main`. Crée une branche : `feat/...`, `fix/...`, `docs/...`, `chore/...` (kebab-case, français sans accents).
- Tu peux commiter et pousser sur ta branche de travail sans demander.
- Ouvre une PR vers `main` : titre au format Conventional Commits, description courte (contexte, changements, comment tester).
- Merge en **squash**. Tu ne merges jamais toi-même une PR : c'est l'utilisateur qui merge.
- Historique linéaire : squash ou rebase uniquement, pas de merge commit. Avant d'ouvrir une PR, rebase ta branche sur `main` (`git rebase origin/main`).
- Le réglage « linear history » du repo GitHub est activé (à faire dans les settings, pas par Claude).
- Jamais de `push --force` (utilise `--force-with-lease` seulement sur ta propre branche, et uniquement si l'utilisateur le demande).
- Ne réécris pas l'historique déjà poussé sur `main`.

## Style de code

- Lis le code voisin avant d'écrire : suis ses conventions, même si tu en préfères d'autres.
- Fais le plus petit changement qui résout le problème. Pas de refactor, de renommage ou de nettoyage hors périmètre.
- Pas de sur-ingénierie : pas d'abstraction, de config ou de paramètre « au cas où ».
- Early return plutôt que des `if` imbriqués. Fonctions courtes, noms explicites.
- Commentaires rares : ils expliquent le **pourquoi**, jamais ce que le code dit déjà.
- Gère les erreurs aux frontières du système (entrées utilisateur, I/O, réseau), pas partout.
- Pas de code mort, pas de `console.log` / `print` de debug laissé dans le code.

## Tests

- Tout changement de comportement vient avec un test. Un bug corrigé vient avec un test qui l'aurait attrapé.
- Teste le comportement, pas l'implémentation.
- Ne supprime pas et n'affaiblis pas un test pour le faire passer : corrige le code, ou dis pourquoi le test est faux.
- Lance d'abord le test concerné, puis la suite complète avant de pousser.

## Sécurité et dépendances

- Jamais de secret, token ou clé dans le code, les logs, les commits ni les messages. Utilise des variables d'environnement. `.env` reste dans `.gitignore`.
- Ne lis pas et n'affiche pas le contenu de fichiers `.env`, clés privées ou credentials.
- Pas de données personnelles dans les logs.
- N'ajoute une dépendance qu'en cas de vrai besoin : dis laquelle, pourquoi, et préfère la stdlib.
- Versions épinglées et lockfile commité. Installe avec `npm ci` (ou équivalent), jamais `npm install` en CI.
- Scripts de cycle de vie désactivés quand c'est possible (`--ignore-scripts`), et exécutés explicitement.
- Ne télécharge et n'exécute jamais de script distant (`curl ... | sh`) sans l'accord de l'utilisateur.

## Demande avant d'agir

Demande une confirmation explicite avant de :

- supprimer des fichiers ou des branches, ou toute action destructive (`rm -r`, `reset --hard`, `DROP`, `TRUNCATE`) ;
- modifier la CI, les workflows, les migrations de base de données ou la config de déploiement ;
- changer la version d'une dépendance majeure ou la version publiée du projet ;
- toucher aux fichiers générés (`dist/`, lockfiles édités à la main).

## Sessions cloud et autonomes

Sans supervision en direct, sois plus prudent, pas plus audacieux :

- Travaille uniquement sur une branche dédiée, ouvre une PR, ne merge pas.
- Ne modifie pas la CI ni les secrets pour « faire passer » un build : signale le problème dans la PR.
- Si une tâche est ambiguë, choisis l'interprétation la plus conservatrice et note ton hypothèse dans la description de la PR.
- Termine par un résumé : ce qui est fait, ce qui reste, ce qui a été vérifié (tests lancés ou non).

## Travailler avec moi

- Réponses courtes et directes. Donne une recommandation plutôt qu'un inventaire d'options.
- Si un test, un lint ou une commande échoue, dis-le avec la sortie. Ne prétends jamais que c'est vérifié si ça ne l'est pas.
- Dis ce que tu as sauté ou ce dont tu n'es pas sûr.
