# Guide des livrables du PEP (Mastère EADL, RNCP39765)

Synthèse de l'« Annexe 1 – Présentation détaillée du PEP » (EFREI, Direction des Études PEX). Titre visé : **Expert en Architecture et Développement Logiciel**.

## Vue d'ensemble

| Livrable | Contenu | Volume | Dépôt PDF | Validation |
|---|---|---|---|---|
| Mission 1 | Présentation de l'entreprise et du contexte de travail | ~20 pages | non précisé | maître d'apprentissage |
| Mission 2 | Mission technique réalisée (S2 de la 1re année) | 30 pages hors annexes | `EADL_Mission2_Nom_Prenom.pdf` | maître d'apprentissage |
| Mission 3 (PEP) | Bilan de projet + rapport d'amélioration continue | ~50 pages, annexes incluses | `EADL_PEP_M3_NOM_PRENOM.pdf` | soutenance |

La Mission 2 fait la transition entre le contexte d'entreprise (Mission 1) et le PEP final (Mission 3, à forte dimension stratégique).

## Conseils communs aux trois livrables

- Décrire la **pratique réelle** de l'entreprise, pas la théorie : organisation du travail, nommage et fusion des branches, déploiements.
- Cibler l'entité d'accueil et l'équipe de rattachement, pas tout le groupe.
- Pas de mode d'emploi du projet, pas de code. Résumer le contexte en quelques lignes et détailler les **activités** (ex. « ajout d'un tri sur l'écran des adhérents »).
- **Quantifier** : durées, volumes, nombre de tickets ou d'incidents traités.
- **Hiérarchiser** : détailler ce qui vaut le plus (compétences, difficulté, enjeux), résumer le reste en liste « j'ai aussi eu à… ».
- Ne pas s'excuser de ne pas suivre une méthode nommée : il y a toujours une organisation du travail à décrire.

## Mission 1 : présentation de l'entreprise

Réalisée à l'arrivée dans l'entreprise.

### Plan attendu

1. **Entreprise et service d'accueil** : raison sociale, secteur, positionnement, chiffres clés, équipe d'affectation, poste et missions.
2. **Contexte de travail** :
   - méthodologie (Agile/Scrum, Kanban, cycle en V…) ;
   - outils collaboratifs (Git, Jira, Trello, Slack, Teams…) ;
   - environnement technique : technologies, gestion de versions et intégration continue, environnements (dev, recette, production), bonnes pratiques (tests, revues de code, déploiements, documentation).
3. **Compte rendu d'activités** : projets confiés, activités réalisées, exemple concret de contribution significative, compétences mobilisées ou développées.
4. **Conclusion et perspectives** : apprentissages, pistes d'évolution.

### Critères de la grille

- Forme : présentation, aspect rédactionnel (maîtrise du français jusqu'à 6 points), esprit de synthèse.
- Contenu (jusqu'à 10 points) : présentation de l'entreprise, écosystème technique et méthodologique, **cartographie synthétique du système d'information**, premières activités et compétences.

## Mission 2 : présentation d'une mission réalisée

Démontrer qu'on mène à bien une **mission technique et organisationnelle** : de la problématique à la solution logicielle ou d'architecture. Compétences visées : conception, développement, qualité, sécurité, industrialisation, amélioration continue.

### Plan attendu (30 pages hors annexes)

| Partie | Pages | Contenu |
|---|---|---|
| 1. Introduction | 3-4 | contexte métier et technique, problématique, objectifs (critères de succès, contraintes, livrables), acteurs, KPI |
| 2. Architecture et conception | 8-10 | principes d'architecture (hexagonale, microservices, MVC), UML (cas d'utilisation, classes, séquences, activité), choix technologiques, faisabilité et comparaison d'alternatives, justification (performance, sécurité, interopérabilité, budget) |
| 3. Réalisation et preuves | 10-12 | solution développée, TDD et tests automatisés (couverture, résultats), pipeline CI/CD, DevSecOps (vulnérabilités, données), preuves objectives (captures, logs, SonarQube, tests de charge) |
| 4. Résultats et bilan critique | 4-5 | résultats vs objectifs, impact qualité/sécurité/performance, difficultés, limites, perspectives pour le PEP |
| 5. Conclusion et retour d'expérience | 2 | compétences et progrès, bénéfices (entreprise, candidat), enjeux du PEP final |

Annexes : schémas, KPI, scripts de tests, feuilles de route.

### Critères de la grille

- Compte rendu (0 à 4) : environnement et contexte, méthodologie réellement pratiquée, écosystème technique, problématique et objectifs, cartographie.
- Travail réalisé (0 à 6) : activités et livrables, démarche et raisonnement, qualité et preuves, résultats, prise de hauteur.
- Attendu de niveau 7 : **justification des choix, preuves, prise de hauteur**.

## Mission 3 : Projet d'Étude Professionnel

Épreuve terminale certificative : une situation professionnelle réelle et complexe, avec un haut niveau d'autonomie. Elle suppose une démarche d'expertise complète : analyse et diagnostic, conception et réalisation argumentées, mesure de l'impact par l'amélioration continue (qualité, performance, sécurité, industrialisation).

Domaines évalués : expertise d'architecture logicielle, mise en œuvre et gestion de projet, amélioration continue et innovation, communication et professionnalisme.

### Partie 1 : Bilan de projet

1. **Introduction et contexte** : entreprise, service, produits ; contexte stratégique et enjeux ; rôle et responsabilités du candidat.
2. **Objectifs** : indicateurs de succès (KPI, baseline) ; contraintes budgétaires, temporelles, réglementaires, techniques.
3. **Analyse et conception** : besoins (utilisateurs, techniques, organisationnels), état de l'art et veille avec sources citées, UML, architecture (hexagonale, microservices, cloud), choix technologiques argumentés.
4. **Réalisation** : phases, jalons, outils collaboratifs, gestion Agile ; modules et services développés ; TDD, CI/CD, DevSecOps ; preuves (logs, tableaux de tests, KPI, graphiques de performance).
5. **Résultats et bilan critique** : résultats vs objectifs, qualité/performance/sécurité, écarts et difficultés, enseignements et pistes d'amélioration.

### Partie 2 : Rapport d'amélioration continue

1. **Diagnostic et mesure initiale** : situation de référence (dette technique, incidents, qualité, performance) et indicateurs de départ (KPI, baseline, logs, taux d'erreur, couverture de tests).
2. **Démarche d'amélioration** : axes d'optimisation, méthode PDCA ou équivalente, actions et outils (SonarQube, ZAP, GitLab CI…).
3. **Mesures et résultats** : comparaison avant/après, analyse d'impact (technique, organisationnel, économique).
4. **Plan de pérennisation** : capitalisation (Definition of Done, rituels d'équipe), intégration dans le cycle de vie des projets.
5. **Conclusion personnelle** : apports pour l'entreprise et le candidat, rôle de l'expert en architecture logicielle dans la transformation numérique.

### Barème du rapport (sur 20)

| Bloc | Critère | Points |
|---|---|---|
| Rédaction | Présentation (mise en page, lisibilité) | -2 à 0 |
| | Aspect rédactionnel | 0 à 2 |
| | Esprit de synthèse | 0 à 2 |
| | Minoration : nombre de pages, fautes d'orthographe | -1 à 0 chacune |
| Contenu | Bilan de projet | 0 à 6 |
| | Rapport d'amélioration continue | 1 à 9 |
| | Bibliographie | 0 à 1 |

Le rapport d'amélioration continue est le bloc le plus pondéré.

## Soutenance

Devant un jury de professionnels et de représentants pédagogiques. Le jury ne juge pas l'exactitude des solutions mais la capacité à **comprendre et articuler la mission**, analyser les enjeux, formuler des recommandations et garantir leur faisabilité. Présentation synthétique, appuyée de preuves concrètes (dashboards, schémas, démonstrations).

### Déroulé recommandé

| Temps | Partie | Intention |
|---|---|---|
| 3 min | Introduction générale | candidat, entreprise, rôle, fil conducteur, problématique |
| 5 min | Livrable 1 : entreprise, SI, premiers constats | organisation, SI, exploitation/sécurité, contraintes, risques, premiers KPI |
| 7 min | Livrable 2 : mission significative | objectifs, choix, mise en œuvre, preuves, résultats mesurés, limites |
| 8 min | Livrable 3 : PEP et amélioration continue | architecture cible, sécurité, conformité, performance, plan d'amélioration, impacts |
| 4 min | Analyse transversale | montée en responsabilité, compétences, arbitrages, risques résiduels, recul |
| 3 min | Conclusion | valeur créée, recommandations, pérennisation, perspectives |

### Critères de la grille orale

- Forme : structure et déroulé (0 à 6), qualité du support (0 à 4). Minorations : respect de la durée, lecture des notes, fautes d'orthographe.
- Fond : compte rendu de l'entreprise, du contexte, de la méthodologie et de l'écosystème technique (0 à 7) ; présentation du travail réalisé, démarche, résultats, réponses au jury (0 à 3).

## Points à clarifier avec l'école

Brouillon de message, sans destinataire.

> **Objet : Questions sur l'Annexe 1 du PEP (EADL, RNCP39765)**
>
> Bonjour,
>
> En préparant mes livrables à partir de l'Annexe 1, j'ai relevé quelques points qui me semblent incohérents ou ambigus, et sur lesquels j'aimerais votre confirmation :
>
> 1. **Durée de la soutenance (p. 123 et 126-127).** Le document annonce 25 min de présentation + 20 min de questions (p. 123), une soutenance de 45 min dont une structure recommandée de 30 min (p. 126), et un critère de minoration sur le « respect de la durée (15 mn) » (p. 127). Quelle durée de présentation faut-il respecter ?
> 2. **Grille d'évaluation de la Mission 2 (p. 122).** Les critères du « compte-rendu » (environnement, méthodologie, cartographie du SI…) reprennent ceux de la Mission 1. Ils ne correspondent pas au plan demandé p. 120-121 (architecture et conception, réalisation et preuves, bilan critique). Quels critères seront réellement appliqués ?
> 3. **Format de dépôt de la Mission 1 (p. 118).** Les Missions 2 et 3 précisent un nom de fichier PDF, mais pas la Mission 1. Quel format et quel nom utiliser ?
> 4. **Barème du rapport d'amélioration continue (p. 126).** L'échelle va de 1 à 9, alors que les autres critères commencent à 0. S'agit-il d'un minimum garanti de 1 point, ou d'une coquille ?
> 5. **Soutenance et livrables précédents (p. 126).** Le déroulé consacre 5 min à la Mission 1 et 7 min à la Mission 2, mais la grille orale (p. 127) évalue le fond sur « compte rendu » et « travail réalisé ». Le rapport de la Mission 3 est-il bien le support principal de l'oral ?
>
> Merci d'avance.
> Cordialement,

## Checklist avant dépôt

- [ ] Volume respecté (20 / 30 hors annexes / ~50 pages).
- [ ] Validation du maître d'apprentissage obtenue (Missions 1 et 2).
- [ ] Chaque choix technique est justifié et comparé à des alternatives.
- [ ] Chaque affirmation clé a une preuve (log, capture, métrique, KPI).
- [ ] Avant/après chiffré dans le rapport d'amélioration continue.
- [ ] Sources citées et bibliographie.
- [ ] Orthographe relue.
- [ ] Nom de fichier conforme et export PDF avec annexes.
