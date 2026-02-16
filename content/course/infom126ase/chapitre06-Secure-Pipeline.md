# Sécuriser la livraison logicielle et la pipeline de développement

> Public cible : étudiants universitaires en Ingénierie logicielle.
> Enseignant : Xavier Devroey.

## Introduction

La sécurité logicielle est devenue un enjeu majeur, tant pour des raisons économiques que géopolitiques. Les attaques sur la chaîne d’approvisionnement logicielle se multiplient, rendant indispensable l’intégration de la sécurité dans le cycle de développement et la sécurisation des pipelines CI/CD. Ce chapitre vise à :

- Comprendre les risques liés à la livraison logicielle et aux pipelines.
- Identifier les bonnes pratiques pour livrer un logiciel sécurisé.
- Explorer les frameworks et outils pour sécuriser la chaîne de production.

## 1. Livrer un logiciel sécurisé

### Principes fondamentaux

La sécurité de l’information (Infosec) repose sur trois piliers :
- **Confidentialité** : accès réservé aux personnes autorisées.
- **Intégrité** : données exactes et non modifiées de manière non détectée.
- **Disponibilité** : systèmes et canaux fonctionnels et fiables.

### Problèmes des approches traditionnelles

Historiquement, la sécurité était traitée en silo, souvent en fin de cycle, ce qui entraînait des retards et des failles. L’approche moderne consiste à intégrer Infosec dans les pratiques DevOps et Agile.

### Bonnes pratiques

- Intégrer la sécurité dans les démonstrations Agile pour feedback précoce.
- Traquer les vulnérabilités dans le même système que les autres défauts (JIRA, GitHub Issues).
- Mettre en place des **repositories uniques** pour le code, les dépendances et les configurations.
- Utiliser des **librairies pré-approuvées** pour les services critiques (authentification, chiffrement).
- Former les développeurs et partager les connaissances.

> **Exemple : Incident XZ Utils (2024)**
> Une backdoor a été introduite dans la librairie XZ Utils, utilisée par SSH. L’attaque a duré trois ans, avec une prise de contrôle progressive du projet open source. Cet incident illustre l’importance de surveiller les dépendances et de vérifier leur provenance.

## 2. Sécuriser la pipeline de développement

Les pipelines CI/CD sont des cibles privilégiées. Une compromission peut injecter du code malveillant dans les builds.

### Framework SLSA ([slsa.dev](https://slsa.dev))

SLSA définit des niveaux de sécurité pour la chaîne logicielle et introduit la notion de **provenance** : métadonnées vérifiables sur le processus de build.

- Attestations basées sur le framework [in-toto](https://slsa.dev/spec/v1.2/attestation-model).
- Contrôles pour le code source, le processus de build, la publication et la distribution.

> **Exemple : SolarWinds (2020)**
> Compromission de la plateforme de build Orion via le malware SUNSPOT. L’attaque a duré plusieurs mois avant d’être détectée.

## 3. Évaluer la posture de sécurité

Le modèle [OWASP SAMM](https://owaspsamm.org) propose 15 pratiques réparties en 5 fonctions (Gouvernance, Design, Implémentation, Vérification, Opérations).

- Chaque pratique comporte 3 niveaux de maturité.
- Exemple : *Secure Build* couvre le processus de build et la gestion des dépendances.

## Résumé – Points clés

- La sécurité doit être intégrée dès le début du cycle.
- Automatisation et visibilité sont essentielles.
- Les dépendances et pipelines sont des surfaces d’attaque critiques.
- Utiliser des frameworks comme SLSA et SAMM pour structurer les pratiques.
