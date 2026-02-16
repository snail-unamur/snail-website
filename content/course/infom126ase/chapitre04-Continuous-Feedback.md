# Continuous Feedback

**Contexte et objectifs**

Ce chapitre présente le concept de *Continuous Feedback* dans le cadre du DevOps et de l'ingénierie logicielle. L'objectif est de comprendre pourquoi et comment mettre en place des boucles de rétroaction (feedback et feedforward) pour améliorer la qualité, la réactivité et la résilience des systèmes logiciels complexes.

## 1. Pourquoi le Continuous Feedback est essentiel

Les systèmes modernes sont complexes et critiques. Les conséquences d'une panne peuvent être catastrophiques (perte de données, impact business, réputation).
Les boucles de feedback permettent :
- De détecter les problèmes tôt, quand ils sont moins coûteux à corriger.
- De prévenir les incidents majeurs par des alertes proactives.
- De favoriser l'apprentissage organisationnel plutôt que la culture du blâme.

**Exemple concret :** Chez Worldline, une panne du système de paiement la veille de la fête des mères a paralysé les transactions en Belgique. Grâce à la télémétrie, le problème a été identifié et corrigé par une mise à jour permettant le mode hors ligne.
**Culture Toyota :** L'Andon cord illustre la philosophie du swarming : arrêter la production et mobiliser l'équipe pour résoudre immédiatement le problème.

## 2. Définir la télémétrie

La télémétrie est un processus automatisé de collecte et transmission de données pour le monitoring.
Elle doit couvrir plusieurs niveaux :
- **Business** : transactions, taux de conversion, churn.
- **Application** : temps de réponse, erreurs.
- **Infrastructure** : CPU, mémoire, réseau.
- **Pipeline de déploiement** : statut des builds, temps d'exécution.

**Bonnes pratiques :**
- Éviter les silos (Dev vs Ops).
- Centraliser la télémétrie pour une vue globale.
- Utiliser des frameworks comme *OpenTelemetry*.

## 3. Analyser la télémétrie

L'analyse proactive permet de détecter des signaux faibles avant la catastrophe.
Techniques :
- Détection d'outliers (ex. Netflix tue automatiquement les nœuds anormaux).
- Moyenne et écart-type pour alertes dynamiques.
- Régressions et FFT pour données non gaussiennes.
- Anomaly detection pour séries temporelles.

**Exemple :** Adyen utilise la stack ELK (Elasticsearch, Logstash, Kibana) pour monitorer les paiements et visualiser les métriques en temps réel.

## 4. Logging et bonnes pratiques

Le logging est la base de la télémétrie applicative.
- Chaque fonctionnalité importante doit générer des logs.
- Choisir le bon niveau : DEBUG, INFO, WARN, ERROR, FATAL.
- Attention à la performance (utiliser SLF4J avec placeholders).
- Respecter la confidentialité (RGPD).

**Exemple :** XWiki impose des règles strictes : pas de stack trace pour WARN, logs utiles et concis.
**Faille Log4j :** illustre l'importance des choix de librairies et de la sécurité.

## Résumé – Points clés

- Le feedback continu est vital pour la qualité et la résilience.
- La télémétrie doit être pensée dès la conception.
- Centralisation et analyse proactive réduisent le MTTR.
- Logging efficace = observabilité + performance + sécurité.

## Références

- Kim et al., *The DevOps Handbook*, IT Revolution, 2021.
- Forsgren et al., *Accelerate*, IT Revolution, 2018.
- Hendrickson, E., *It’s All About Feedback*, DOES15.
- Turnbull, *The Art of Monitoring*.
- Documentation Elastic (ELK Stack).
- XWiki Logging Guidelines.
