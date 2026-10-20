# Mission 2 : plan détaillé du rapport

Rapport de 30 pages hors annexes, validé par le maître d'apprentissage. Dépôt : `EADL_Mission2_Nom_Prenom.pdf`. Source : Annexe 1 du PEP (p. 120-122). Les pages de chaque partie viennent du PDF ; le découpage en sous-sections est une proposition.

Attendu de niveau 7 : **justification des choix, preuves, prise de hauteur**.

## 1. Introduction (3-4 pages)

- 1.1 Contexte métier et technique (1 p.) : `<à compléter>`
- 1.2 Problématique : dysfonctionnement, besoin d'évolution, dette technique, performance ou sécurité (1 p.) : `<à compléter>`
- 1.3 Objectifs : critères de succès, contraintes, livrables (0,5 p.)
- 1.4 Acteurs internes et externes (0,5 p.)
- 1.5 KPI retenus et valeurs de départ (0,5 p.)

## 2. Architecture et conception (8-10 pages)

- 2.1 Choix d'architecture et principes retenus (hexagonale, microservices, MVC…) (2 p.)
- 2.2 Modélisation UML (3 p.) : cas d'utilisation, classes, séquences, activité. Seuls les diagrammes utiles, commentés.
- 2.3 Choix technologiques (2 p.) : frameworks, outils CI/CD, bases de données, sécurité.
- 2.4 Faisabilité et alternatives (1-2 p.) : tableau comparatif avec critères pondérés.
- 2.5 Justification des choix (1 p.) : performance, sécurité, interopérabilité, budget.

## 3. Réalisation et preuves (10-12 pages)

- 3.1 Solution développée : fonctionnalités, modules, interfaces (2-3 p.)
- 3.2 TDD et tests automatisés (2 p.) : scripts, couverture, résultats.
- 3.3 Pipeline CI/CD (2 p.) : étapes, outils, résultats de build et de déploiement.
- 3.4 DevSecOps (2 p.) : analyse de vulnérabilités, sécurisation des données.
- 3.5 Preuves objectives (2-3 p.) : captures, logs, métriques (SonarQube, tests de charge…).

Pas de code dans le corps du rapport : le renvoyer en annexe si utile.

## 4. Résultats et bilan critique (4-5 pages)

- 4.1 Résultats obtenus vs objectifs initiaux : tableau KPI avant/après.
- 4.2 Impact sur la qualité, la sécurité, les performances.
- 4.3 Difficultés rencontrées et solutions adoptées.
- 4.4 Limites et axes d'amélioration.
- 4.5 Perspectives pour le PEP (Mission 3).

## 5. Conclusion et retour d'expérience (2 pages)

- Compétences mobilisées et progrès réalisés.
- Bénéfices pour l'entreprise et pour le candidat.
- Enjeux identifiés pour le PEP final.

## Annexes

Schémas, KPI, scripts de tests, feuilles de route et tout autre document pertinent.

## Correspondance avec la grille (p. 122)

| Critère | Où le traiter |
|---|---|
| Compte rendu (0-4) : environnement, méthodologie, écosystème, problématique, cartographie | partie 1 et 2.3 |
| Activités et livrables | 3.1 |
| Démarche et raisonnement | partie 2 |
| Qualité et preuves | 3.2 à 3.5 |
| Résultats obtenus | partie 4 |
| Prise de hauteur | 4.4, 4.5 et partie 5 |

La grille ne cite pas explicitement l'architecture, l'UML ou le DevSecOps. Le plan les traite quand même, car la description de la mission les demande (voir `docs/guide-livrables-pep.md`).

## Checklist
- [ ] 30 pages hors annexes respectées.
- [ ] Chaque choix est comparé à au moins une alternative.
- [ ] Chaque résultat a une preuve datée.
- [ ] KPI avec valeur initiale et finale.
- [ ] Validation du maître d'apprentissage.
