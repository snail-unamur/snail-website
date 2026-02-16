
# Chapitre — Continuous Delivery et pipelines de développement

**Cours : INFOM126 — Automated Software Engineering**  
**Discipline : génie logiciel**  
**Enseignant·e : Xavier Devroey**

> **But du chapitre.** Comprendre comment concevoir, outiller et opérer une *software production pipeline* qui permet l’**intégration continue (CI)**, la **livraison continue (CD)** et, lorsque c’est pertinent, le **déploiement continu**, en s’appuyant sur le contrôle de version, l’automatisation des builds et des tests, et des pratiques d’équipe favorables à la qualité. citeturn2search1turn2search2

---

## Introduction

Dans la plupart des organisations, le passage des commits au logiciel livré repose sur une chaîne d’outils et de pratiques appelée **pipeline de développement**. Elle orchestre la compilation, l’analyse statique, les tests (unitaires, d’intégration, systèmes), l’emballage des artefacts, et finalement la décision de mise en production. L’objectif est de **réduire le temps et l’incertitude** entre le changement de code et sa mise à disposition des utilisatrices et utilisateurs, tout en **maîtrisant les risques**. citeturn2search1turn2search2

### Objectifs d’apprentissage
À l’issue de ce chapitre, vous serez capable de :
- Expliquer les exigences d’une pipeline moderne (environnements « production‑like », self‑service, automatisation). citeturn2search1
- Mettre en place un **référentiel unique de vérité** (code, infra, tests, artefacts) et argumenter son intérêt organisationnel. citeturn2search1turn2search2
- Choisir un **modèle de branches** (mainline integration, feature branching, trunk‑based, release branches/trains) et en évaluer les compromis. citeturn2search1
- Automatiser un **build** avec des outils (Make/Maven/Gradle), gérer les **dépendances** et les **plugins**, et préparer le **déploiement**. citeturn2search1
- Décrire et configurer un **workflow CI/CD** (ex. GitHub Actions/Jenkins) et discuter des défis (versions d’actions, sécurité, obsolescence). citeturn2search1
- Positionner les **tests** dans la pipeline (stratégies, critères d’adéquation, gestion des *flaky tests*, CIT/pairwise). citeturn2search1

> **Remarque (hypothèse).** Le chapitre s’appuie sur un cours de génie logiciel orienté développement d’applications distribuées ; la granularité des exemples suppose un public universitaire familiarisé avec Git et des outils de build (Java, JS). citeturn2search1turn2search2

---

## 1. Fondations d’une pipeline de développement

### 1.1 Vue d’ensemble
Une pipeline typique démarre au **push** ou au **merge** vers le dépôt central, puis déroule : *build* (compilation, analyse statique, tests unitaires, métriques de qualité), *intégration* (tests d’intégration), *capacités* et *performance*, *acceptance* (tests utilisateurs), décision de **release**, déploiement en **production** et tests de fumée. Le périmètre *CI* couvre l’automatisation jusqu’aux tests d’intégration ; **CD** prolonge jusqu’à la décision de publier ; **continuous deployment** pousse automatiquement en production chaque changement validé. citeturn2search1

### 1.2 Exigences clés
- **Environnements production‑like à chaque étape.** On minimise le fameux « *works on my machine* » en rapprochant les environnements de dev/test de la prod. Ces environnements doivent être **créés à la demande**, **automatiquement** et **en self‑service**, à partir d’artefacts sous contrôle de version. citeturn2search1
- **Automatisation et Infrastructure as Code.** Du clonage d’images (VM/AMI/Vagrant) au *bare‑metal provisioning* (PXE), en passant par la configuration (Ansible, Puppet, Chef, Salt) et l’assemblage par **conteneurs** (Docker/Kubernetes), jusqu’au *cloud* (AWS, Azure, GCP) ou PaaS : tout doit être scriptable et rejouable. citeturn2search1
- **Bénéfices attendus.** Provisionner en minutes sans ticket, reproduire/diagnostiquer les défauts sur des bacs isolés, expérimenter sur l’infra, capitaliser un savoir partagé entre Dev et Ops. citeturn2search1

### 1.3 Exemple discuté en cours
Le recours exclusif à des environnements allégés de test peut masquer des écarts de configuration ou de charge et conduire à des incidents lors de la première mise en production. L’usage systématique d’environnements *production‑like* créés *on demand* réduit ce risque et accélère les retours en cas d’incident (recréation automatisée). citeturn2search2

### 1.4 Rebuild > Repair et infrastructure immuable
Traiter l’infrastructure comme **jetable** (cattle, pas pets) : on **reconstruit** plus qu’on ne répare. Les changements passent par le **contrôle de version** et re‑créent des images/infrastructures ; les connexions *admin* directes en prod sont proscrites, voire désactivées. Cette approche facilite le **scaling horizontal**, la **cohérence des configurations** et la **remédiation rapide**. Des *service meshes* ou *parameter stores* aident à propager la configuration d’exécution. citeturn2search1turn2search2

---

## 2. Référentiel unique de vérité et gestion de configuration

### 2.1 Pourquoi un « single source of truth » ?
Mettre **tout ce qui fait tourner le système** sous contrôle de version : code, dépendances, scripts de base de données et de déploiement, fichiers d’infrastructure (IaC, images/containers), configurations cloud, scripts de tests (auto et manuels), documentation, notes de release. But : **reconstituer la production de façon fiable** (et rapide) après incident, comprendre *qui a changé quoi et quand*, et fluidifier la collaboration (Dev, QA, Sec, Ops). citeturn2search1

> Dans la pratique, on répartit ces éléments sur **plusieurs dépôts physiques** : code source (Git), **repositories d’artefacts** (Nexus/Artifactory/S3), **registries de conteneurs** (Docker), chacun avec **empreintes cryptographiques** vérifiées au déploiement. citeturn2search1

### 2.2 SCM : objectifs et activités
Le **Software Configuration Management (SCM)** encadre l’identification des éléments et des **baselines**, le **contrôle des changements** (p.ex. *pull requests*), la **traçabilité** (issues/kanban), l’**audit** de conformité aux spécifications, la **gestion des builds**, des **environnements** et la **coordination d’équipe** (défauts, discussions). citeturn2search1

### 2.3 Systèmes de contrôle de version
- **Centralisés (SVN).** Maître unique, SPOF, branches gérées de façon lourde (copies), deltas cumulatifs. citeturn2search1
- **Distribués (Git).** Chaque clone contient l’historique ; intégrité par hachage ; opérations locales rapides ; modèle en **instantanés** (snapshots) ; favorise l’expérimentation et la résilience. citeturn2search1

---

## 3. Branches, intégration et stratégies de release

### 3.1 Notions et conflits
Une **branche** est une suite de commits dont le **HEAD** est la révision courante. Les **merges** nécessitent parfois une résolution : conflits **textuels** (détectés par Git) vs **sémantiques** (se révèlent au build ou à l’exécution). D’où l’importance des tests automatiques pour sécuriser les intégrations. citeturn2search1

### 3.2 Modèles d’intégration (d’après Fowler)
- **Mainline integration.** Pull → merge/rebase → vérification locale → push sur la mainline *si et seulement si* la branche reste « saine ». citeturn2search1
- **Feature branching.** Une branche par fonctionnalité ; intégrations fréquentes pour réduire la complexité des merges ; souvent couplé aux *pull requests*. citeturn2search1
- **Continuous Integration (CI).** Intégrer **au plus tard en fin de journée**, idéalement plusieurs fois par jour, quitte à masquer une fonctionnalité incomplète par **feature flags**. Bénéfices : feedback rapide, merges plus petits, refactoring encouragé. citeturn2search1
- **Trunk‑Based Development.** Travail majoritairement sur la **mainline** ; branches très **courte durée** (quelques jours au plus) ; release depuis *trunk* ou **release branch** courte. Pratique corrélée à une meilleure performance de livraison. citeturn2search1

### 3.3 Revue de code pré‑intégration et frictions
La **revue systématique** des commits vers la mainline (p.ex. via *pull request*) augmente la qualité et la diffusion de connaissances dans l’équipe, mais attention aux **frictions** (formulaires, validations manuelles, coordinations inter‑équipes) : si elles n’apportent pas de valeur, **automatiser** ou déplacer plus tard dans la pipeline. Intégrer des règles outillées (tests, couverture, analyse statique) pour des décisions reproductibles. citeturn2search1

### 3.4 Stratégies de release
- **Release‑ready mainline.** La tête de *main* est *toujours* déployable ; **CD** décide *quand* publier, **continuous deployment** publie *systématiquement*. citeturn2search1
- **Release branch.** Geler les fonctionnalités, ne prendre que des **fixes**, puis merger ces fixes vers *main*. citeturn2search1
- **Release trains.** Départs à **intervalle régulier** (hebdo/mensuel) ; les équipes choisissent « le train » adapté à l’état de leur feature ; corrections *cherry‑pickées* entre trains. citeturn2search1

> **Point d’attention.** Plus une organisation maintient longtemps des branches de release, plus le **coût de maintenance** des versions anciennes augmente ; d’où l’intérêt de politiques de support claires et d’un encouragement à migrer. citeturn2search1

---

## 4. Automatisation des builds et gestion des dépendances

### 4.1 Du script au système de build
- **Make/Ant** : exécution de cibles/targets (compilation, tests, packaging) via règles déclaratives. citeturn2search1
- **Maven/Gradle/MSBuild** : gestion de **cycle de vie**, **dépendances** (repos central/privé), **plugins** (qualité, reporting, déploiement), **profils**. Philosophie Maven : *convention over configuration*. citeturn2search1

### 4.2 Maven en bref
Structure standard (`src/main/...`, `src/test/...`), **POM** avec `groupId`, `artifactId`, `version` (souvent en **semantic versioning** : MAJOR.MINOR.PATCH), type de **packaging** (`jar`, `war`, `pom`), **modules** et **phases** (`compile`, `test`, `package`, `install`, `deploy`). Les **plugins** (ex. JaCoCo, Sonar) s’attachent à des phases pour enrichir le pipeline qualité. citeturn2search1

### 4.3 Dépendances et artefacts
Les dépendances proviennent de **repositories** (Maven Central, private Nexus/Artifactory). On versionne les **définitions** (numéros fixes ou propriétés), on signe/valide les **hashes** des artefacts, et on **publie** (déploiement) selon des profils adaptés (ex. *release*). Des outils comme **Dependabot** aident à la mise à jour proactive. citeturn2search1

---

## 5. Intégration continue sur serveur : GitHub Actions & Jenkins

### 5.1 Concepts communs
Un **workflow** (fichier YAML, Jenkinsfile, etc.) décrit **quand** déclencher (évènement, planification, manuel, API), **où** exécuter (runner/agent éphémère), **quoi** faire (jobs parallélisables, étapes scriptées ou **actions** réutilisables). Chaque exécution est isolée et fournit un **reporting** pour le diagnostic. citeturn2search1

### 5.2 Exemple de chaîne CI/CD
Construire → tester (unitaires, intégration, end‑to‑end) → contrôler la qualité (couverture, analyse statique) → empaqueter → publier artefacts → déployer (si politique **CD** l’autorise) → monitorer et collecter les indicateurs. Des projets comme **XWiki** exposent des pipelines Jenkins multi‑jobs (build, quality, test‑release) avec temps d’exécution significatifs dû aux tests système. citeturn2search1

### 5.3 Défis de l’écosystème Actions
- **Obsolescence** : quand et comment mettre à jour ?  
- **SémVer** : major/minor/patch — GitHub recommande le **pinning sur la major** pour bénéficier des correctifs compatibles, au prix d’un risque résiduel.  
- **Sécurité** : surface d’attaque accrue via actions tierces ; attention aux secrets et aux permissions.  
- **Abandon/dépréciation** des actions.  
Ces enjeux imposent des politiques de **pinning**, de **revue** des dépendances CI et de **surveillance** continue. citeturn2search1

---

## 6. Tests automatisés dans la pipeline

### 6.1 Panorama
- **Unitaires** : rapides, contrôlables ; ne couvrent pas les interactions complexes.  
- **Intégration** : valident les échanges avec DB/services/bibliothèques externes ; plus coûteux.  
- **Systèmes (end‑to‑end)** : boîtes noires proches du réel (ex. Selenium/WebDriver/IDE) ; lents, fragiles, exigent des environnements dédiés. citeturn2search1

### 6.2 Critères d’adéquation
- **Couverture requirements/scénarios** (TDD/BDD avec Gherkin/Cucumber).  
- **Couverture structurelle** (lignes, branches, **MC/DC** quand pertinent).  
- **Couverture de configurations** (voir § 6.3). citeturn2search1

### 6.3 Tester les configurations : CIT / pairwise
Lorsque le SUT doit tourner sur de multiples **configurations** (types d’appareils, versions d’OS, tailles d’écran, CPU…), le **Combinatorial Interaction Testing (CIT)** vise à couvrir toutes les combinaisons de *t* facteurs (souvent **t = 2**, *pairwise*) pour réduire drastiquement le nombre de cas (ex. 96 combinaisons → 16 cas pairwise). Des services comme **Firebase Test Lab** facilitent l’exécution multi‑devices. citeturn2search1

### 6.4 *Flaky tests*
Des tests **non déterministes** (réseau, temps, concurrence, asynchronisme, aléatoire/ML, I/O, GUI, dépendances d’ordre, timeouts, plateformes) gaspillent du temps, masquent des régressions et érodent la confiance. Bonnes pratiques : stabiliser le temps (mocks/fournisseurs dédiés), contrôler l’aléa (seed), isoler les ressources, supprimer les dépendances d’ordre, monitorer la **flakiness** (ex. visualisations type Spotify/Odeneye) et instaurer une politique de **quarantaine/réparation**. citeturn2search1

---

## 7. Bonnes pratiques et erreurs fréquentes

- **Tout mettre sous contrôle de version** (y compris infra et données de configuration), mais **never** commiter de secrets : utiliser des *secret stores* et des permissions minimales. citeturn2search1turn2search2
- **Automatiser la création des environnements** et imposer le **self‑service** pour supprimer les files d’attente et divergences de config. citeturn2search1
- **Protéger la branche principale** et exiger des **revues** outillées (tests, couverture, analyse) avant merge. Réparer **en priorité** tout build rouge. citeturn2search1
- **Favoriser l’intégration fréquente** (CI) et, pour des fonctionnalités incomplètes, recourir aux **feature flags** temporaires. citeturn2search1
- **Signer et vérifier** les artefacts ; consigner les **hashes** et vérifier à l’installation/déploiement. citeturn2search1
- **Mesurer et reporter** : temps de build, taux de réussite, couverture, flakiness, MTTR… pour piloter l’amélioration continue. citeturn2search1

---

## Résumé — points clés à retenir

1. Une pipeline efficace s’appuie sur des **environnements production‑like**, **IaC** et un **référentiel unique de vérité**. citeturn2search1
2. Le **SCM** structure les identifications, changements, baselines, audits et builds, et le contrôle de version doit couvrir **code et environnements**. citeturn2search1
3. Les modèles de branches (**CI**, **feature branching**, **trunk‑based**) et de **release** (mainline prête, branche de release, **release trains**) sont des **trade‑offs** à choisir consciemment. citeturn2search1
4. Les systèmes de **build** modernes (Maven/Gradle) gèrent dépendances, plugins et phases de cycle de vie jusqu’au **déploiement**. citeturn2search1
5. Les plateformes CI/CD (**GitHub Actions**, **Jenkins**) orchestrent workflows, jobs et runners, mais exigent une gestion active des **dépendances CI** et des **secrets**. citeturn2search1
6. Les **tests** doivent être positionnés intelligemment (du **unitaire** au **système**), avec des critères d’adéquation clairs, la prise en compte des **configurations** (CIT) et la lutte contre la **flakiness**. citeturn2search1

---

### Références et ressources (issues du cours)
- DevOps Handbook ; Accelerate (Forsgren, Humble, Kim) : facteurs de performance, CI/CD, culture. citeturn2search1
- Martin Fowler — **Branching patterns**, **Feature Toggles**. citeturn2search1
- Docs Git, Maven, GitHub Actions ; exemples Jenkins/XWiki. citeturn2search1

