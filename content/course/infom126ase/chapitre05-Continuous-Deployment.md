
# INFOM126 — Chapitre 5 : Continuous Deployment et Infrastructure as Code

> **Cours :** Automated Software Engineering (niveau Master)
> 
> **Objectif du chapitre :** comprendre comment passer d’une version prête à être livrée à un déploiement fiable et reproductible, en s’appuyant sur l’Infrastructure as Code (IaC) et des stratégies de déploiement (
Blue‑Green, Canary), tout en maîtrisant les fondements (virtualisation, conteneurisation, cloud) et les bonnes pratiques (tests, contrôle de version, gestion des secrets).

---

## Introduction

Dans une pipeline CI/CD, le **continuous deployment** correspond à la **mise en production automatisée** des artefacts validés par les étapes de build, analyse, tests unitaires et d’intégration, tests de capacité et d’acceptation. L’objectif n’est pas uniquement de “pousser” une nouvelle version, mais de **contrôler le risque, la réversibilité et l’observabilité**, en orchestrant à la fois l’application, son infrastructure, ses données et la télémétrie.

**Objectifs d’apprentissage :**
- Décrire les composants d’une infrastructure moderne (VMs, hyperviseur, conteneurs, services cloud).
- Expliquer le rôle de l’IaC et distinguer les approches **déclarative** et **impérative**, ainsi que les modes **push** et **pull**.
- Mettre en œuvre des **stratégies de déploiement** (Blue‑Green, Canary) et leur gestion des données.
- Appliquer les **bonnes pratiques** (versioning, tests des configurations, modularité, secrets).

**Figure 1 — Vue d’ensemble d’une pipeline CI/CD.** De gauche à droite : dépôt du code → build (compilation, analyse statique, tests unitaires, qualité) → intégration (tests d’intégration, performance/capacité) → acceptation (tests utilisateurs, validation) → release → déploiement (smoke tests, mise en production).

---

## 1. Infrastructure pour le déploiement

### 1.1. Limites des approches manuelles
Historiquement, l’infrastructure était **provisionnée et configurée à la main** (tickets au support, connexions SSH, scripts ad hoc). Cette approche entraîne :
- **Coûts et lenteur** (tâches répétitives, faible passage à l’échelle).
- **Configuration drift** : des serveurs supposés identiques dérivent au fil des changements non coordonnés.
- **Visibilité réduite** pour les développeurs : hypothèses erronées sur l’état réel des environnements.

L’objectif moderne est d’avoir une **infrastructure plus facile à reconstruire qu’à réparer** : on privilégie des environnements reproductibles, que l’on peut recréer rapidement après incident, et sur lesquels **les changements sont décrits, versionnés et propagés automatiquement**.

### 1.2. Virtualisation : VMs et hyperviseur
Une **machine virtuelle (VM)** se comporte comme un ordinateur complet, isolé du matériel sous‑jacent. Deux grandes familles :
- **Full virtualization** : le système invité est complètement isolé; l’hyperviseur émule l’environnement matériel.
- **Paravirtualization** : l’OS invité coopère avec l’hyperviseur via des interfaces spécifiques, pour réduire la sur‑couche.

Les hyperviseurs peuvent être de **type 1** (bare‑metal, sur le matériel) ou **type 2** (hébergés sur un OS). La virtualisation facilite la consolidation des charges, l’isolation et la reprise après sinistre, mais **réplique un OS par VM**, avec l’empreinte associée.

**Figure 2 — Hyperviseur type 1 vs type 2.** Type 1 : exécution directe sur le matériel et hébergement de VMs. Type 2 : exécution au‑dessus d’un OS hôte qui héberge les VMs.

> *Références :* aperçu des différences full/paravirtualization et hyperviseur [GeeksforGeeks], [Wikipedia — Hypervisor].

### 1.3. Conteneurisation : Docker et écosystème
Les **conteneurs** (ex. Docker) packagent une application avec ses bibliothèques et sa configuration, en s’appuyant sur la **virtualisation au niveau de l’OS** (partage du même noyau). Avantages :
- **Empreinte plus faible** que des VMs (pas d’OS complet par instance).
- **Démarrage rapide**, densité élevée, portabilité.
- **Images** immutables et reproductibles; **registry** pour distribuer les images; **daemon/client** pour piloter les conteneurs; **services** pour la montée en charge.

**Figure 3 — Architecture Docker.** Client CLI ↔ daemon; images ↔ registry; exécution en conteneurs; services pour l’orchestration multi‑daemons.

> *Références :* Docker et concepts d’architecture [Wikipedia — Docker], [GeeksforGeeks — Architecture of Docker].

**Exemple : Dockerfile minimal pour une application web Java (inspiré de XWiki, reformulé).**
```dockerfile
# Base image : Tomcat officiel
FROM tomcat:10-jdk17

# Variables d’environnement (exemple)
ENV XWIKI_VERSION=15.10.1 \
    JAVA_OPTS="-Xms512m -Xmx1024m"

# Copie des artefacts (war) construits par la pipeline
COPY target/app.war /usr/local/tomcat/webapps/ROOT.war

# Configuration (ex. fichiers de conf)
COPY conf/server.xml /usr/local/tomcat/conf/server.xml

# Commande de démarrage
CMD ["catalina.sh", "run"]
```
Cet exemple illustre la **déclarativité** du packaging (image de base, artefacts, configuration) et **l’immutabilité** : on reconstruit une image plutôt que de modifier une instance en place.

### 1.4. Modèles cloud : IaaS, PaaS, SaaS
Selon le niveau d’abstraction géré par le fournisseur :
- **IaaS** : vous gérez l’OS, la configuration et le runtime; le fournisseur provisionne le réseau/stockage/serveurs.
- **PaaS** : vous déployez vos applications et données; le fournisseur gère OS, middleware (Java/.NET, base de données, etc.).
- **SaaS** : vous consommez une application prête à l’emploi (ex. WordPress, Odoo), sans gérer le déploiement.

> *Références :* comparatif des modèles cloud [Red Hat — IaaS vs PaaS vs SaaS].

---

## 2. Infrastructure as Code (IaC)

### 2.1. Définition et portée
L’**IaC** consiste à **décrire l’infrastructure dans des fichiers** (templates, scripts, manifestes) placés sous **contrôle de version** et considérés comme **source de vérité**. Le provisioning, la configuration et les mises à jour sont **automatisés**, testés et audités. Cette pratique favorise la **fiabilité**, la **vitesse de livraison** et la **performance organisationnelle**, en ligne avec les résultats empiriques sur DevOps et Continuous Delivery.

> *Références :* impact de l’automatisation du déploiement et des pratiques de livraison sur la performance [Forsgren et al., 2018 — Accelerate].

### 2.2. Approches : déclarative vs impérative
- **Déclarative (what)** : on exprime l’état désiré; l’outil calcule et applique les opérations nécessaires.
- **Impérative (how)** : on liste les commandes à exécuter, étape par étape.

**Exemple déclaratif (Ansible, reformulé)** — mise à jour d’un serveur MySQL :
```yaml
---
- name: Mise à jour et redémarrage de MySQL
  hosts: db_servers
  become: yes
  tasks:
    - name: S’assurer que le paquet mysql-server est à jour
      ansible.builtin.package:
        name: mysql-server
        state: latest
    - name: Redémarrer le service
      ansible.builtin.service:
        name: mysql
        state: restarted
```

**Exemple impératif (Ansible, reformulé)** — configuration par commandes explicites :
```yaml
---
- name: Configuration MySQL impérative
  hosts: db_servers
  become: yes
  tasks:
    - name: Mettre à jour l’index des paquets
      ansible.builtin.command: apt-get update -y
    - name: Installer une version spécifique
      ansible.builtin.command: apt-get install -y mysql-server=8.0.37-0
    - name: Appliquer un fichier de configuration
      ansible.builtin.copy:
        src: files/my.cnf
        dest: /etc/mysql/my.cnf
    - name: Redémarrer le service
      ansible.builtin.command: systemctl restart mysql
```

> *Références :* tutoriels introductifs IaC et Ansible [Invensis Learning — IaC Tutorial], [Codecademy — Infrastructure Configuration].

### 2.3. Modes d’application : push vs pull
- **Push** : un contrôleur (pipeline, orchestrateur) **pousse** la configuration vers les nœuds.
- **Pull** : les nœuds **récupèrent** (pull) leur configuration depuis un serveur central/registry.

Le choix dépend des contraintes réseau, de la sécurité et du besoin de décentralisation. Dans tous les cas, on **minimise la configuration par instance** (adresses, identités) et on privilégie la **configuration dynamique** via un service de registre/paramètres.

> *Références :* modes push/pull en IaC [Invensis Learning — IaC Tutorial].

### 2.4. Outils et catégories
- **Scripting ad hoc** : utile pour des tâches ponctuelles; ne passe pas à grande échelle.
- **Conteneurs et templating** : Docker, Vagrant, Packer pour créer des images pré‑chargées.
- **Orchestration/provisioning d’infrastructure** : Terraform, AWS CloudFormation, OpenStack Heat.
- **Configuration management** : Ansible, Puppet, Chef (déploiement d’apps, dépendances, monitoring).

**Exemple Terraform (reformulé)** — instance EC2 dédiée à l’exécution Docker :
```hcl
provider "aws" {
  region = "eu-west-1"
}

resource "aws_instance" "docker_host" {
  ami           = "ami-0abcd1234efgh5678"   # Hypothèse : AMI Ubuntu récente
  instance_type = "t3.medium"
  user_data     = <<-EOF
                  #!/bin/bash
                  apt-get update -y
                  apt-get install -y docker.io
                  systemctl enable --now docker
                  EOF
  tags = {
    Name = "ci-docker-host"
  }
}
```
> *Références :* exemples Terraform pour AWS + Docker [Futurice — Terraform examples].

### 2.5. Phoenix servers et immutable servers
Pour éviter le **drift** et les changements non testés :
- **Phoenix servers** : lorsqu’un serveur dérive, on **détruit et reconstruit** à partir d’une **image de base** maîtrisée; on gère des **images** plutôt que des patchs invisibles.
- **Immutable servers** : on **ne modifie jamais** un serveur en place; chaque changement passe par la mise à jour d’une image validée par la pipeline, puis **remplacement** des instances.

La configuration par instance se fait via **métadonnées au provisioning** ou via un **registre central** (ex. service mesh, *parameter store*). On réduit le périmètre de ces paramètres pour préserver l’immutabilité et la reproductibilité.

> *Références :* concepts Phoenix et Immutable servers [Martin Fowler — Phoenix Server], [Martin Fowler — Immutable Server].

### 2.6. Bonnes pratiques IaC
- **Tout dans les fichiers de configuration** (source de vérité) et **contrôle de version**.
- **Tester les configurations** (linting, tests d’apply, environnements de pré‑production) et prévoir **rollback**.
- **Approche modulaire** (modules Terraform, rôles Ansible) pour réutiliser et composer.
- **Gestion des secrets** : ne jamais commiter clés/tokens dans le dépôt; utiliser un coffre (Vault, secret manager) et des identités de pipeline.
- **Parité pré‑prod/prod** : garder les environnements aussi proches que possible.

---

## 3. Stratégies de déploiement automatisé

### 3.1. Blue‑Green Deployment
On maintient **deux environnements de production** (Blue et Green) **identiques**. Avant une release, on valide dans l’environnement inactif. Une fois OK, on **bascule le routage** vers cet environnement, qui devient actif. L’autre environnement sert de **filet de sécurité** pour un **rollback instantané**.

**Gestion de la base de données.** Si le **schéma** évolue, on procède en **deux temps** : (1) refactorer le schéma pour **supporter l’ancien et le nouveau modèle**; (2) déployer la nouvelle application; (3) une fois validé, **retirer l’ancien schéma**.

**Figure 4 — Bascule Blue‑Green.** Environnement A (actif) ↔ Environnement B (inactif, staging final) → switch du trafic → capacité de rollback en re‑switch.

> *Références :* description et implications opérationnelles [Martin Fowler — Blue‑Green Deployment].

### 3.2. Canary Release
Déploiement **progressif** : la nouvelle version est exposée à un **sous‑ensemble d’utilisateurs** (aléatoirement, internes, par profil/démographie, ou par **région géographique**), avec **monitoring** rapproché (taux d’erreurs, latence, consommation). Si les indicateurs restent dans les seuils, on **étend** le public jusqu’à la bascule complète.

Inconvénient : on **opère plusieurs versions** en parallèle (complexité de compatibilité et d’observabilité). Avantage : test **en charge réelle** et **réduction du risque**.

**Figure 5 — Déploiement canari (phases).** 5 % des requêtes → 25 % → 50 % → 100 %, avec métriques et garde‑fous.

> *Références :* principes et pratiques du canary release [Martin Fowler — Canary Release].

### 3.3. Données et télémétrie
- **États durables** : externaliser la persistance (bases robustes, journaux, réplication), éviter les writes locales aux serveurs éphémères.
- **Observabilité** : centraliser **logs, métriques, traces**; vérifier que la **télémétrie** n’est pas perdue lors des rotations Blue‑Green/Canary.
- **Compatibilité** : si plusieurs versions cohabitent, garantir la compatibilité des **contrats d’API**, des **schémas de données** et des **formats de messages**.

---

## 4. Mise en pratique : blueprint d’une pipeline de déploiement

1. **Build & packaging**
   - Compiler, tester, analyser; produire artefacts (ex. `app.war`).
   - Construire l’**image Docker** à partir d’une base standard; pousser l’image au **registry privé**.
2. **Provisioning d’infrastructure (IaC)**
   - Terraform (ou CloudFormation/Heat) pour créer réseaux, instances, équilibreurs; labelliser les ressources.
   - Paramétrer l’accès (clés, rôles IAM) **via coffre de secrets**.
3. **Configuration applicative**
   - Rôles Ansible/Puppet/Chef pour configurer services (base de données, caches, monitoring), **sans drift**.
4. **Déploiement contrôlé**
   - **Blue‑Green** ou **Canary** avec règles de routage (load balancer, service mesh).
   - **Smoke tests** post‑déploiement; seuils d’alerte pour déclencher **rollback**.
5. **Observabilité et gouvernance**
   - Logs/métriques/traces centralisés; tableaux de bord; alertes proactives.
   - Audit des changements (commits IaC, numéros de version, approbations de release).

**Exemple de playbook de déploiement (reformulé, simplifié)** :
```yaml
---
- name: Déployer la version validée en Blue-Green
  hosts: green_pool
  become: yes
  vars:
    image: registry.local/app:1.8.0
  tasks:
    - name: Extraire l’image validée
      community.docker.docker_image:
        name: "{{ image }}"
        source: pull
    - name: Démarrer le conteneur
      community.docker.docker_container:
        name: app-green
        image: "{{ image }}"
        env:
          APP_ENV: "prod"
          CONFIG_URL: "https://config.local/"
        published_ports:
          - 8080:8080
        restart_policy: always
    - name: Tests fumée
      ansible.builtin.uri:
        url: http://green-lb.health.local/health
        return_content: yes
      register: health
    - name: Basculer le trafic si OK
      ansible.builtin.debug:
        msg: "Basculer le load balancer vers GREEN (condition: {{ health.status == 200 }})"
```

---

## 5. Résumé — Points clés

- Le **continuous deployment** nécessite une **infrastructure maîtrisée et reproductible**, idéalement **immutable**.
- L’**IaC** donne une **source de vérité versionnée** et **testable** pour provisioning et configuration.
- Choisir l’approche **déclarative** pour exprimer l’état cible et l’outillage adéquat (Terraform, Ansible, Puppet, Chef).
- Les modèles **IaaS/PaaS/SaaS** structurent **qui gère quoi**; la conteneurisation (Docker) optimise la portabilité et la densité.
- Les stratégies **Blue‑Green** et **Canary** réduisent le **risque** et améliorent la **réversibilité**; penser **schémas de données** et **observabilité**.
- **Bonnes pratiques** : tests des configurations, modularité, gestion des secrets, parité pré‑prod/prod, audit.

---

## Références (sélection)

- Forsgren, N., Humble, J., & Kim, G. (2018). *Accelerate: The Science of Lean Software and DevOps*. IT Revolution.  
- Martin Fowler. *Blue‑Green Deployment*. https://martinfowler.com/bliki/BlueGreenDeployment.html  
- Martin Fowler. *Canary Release*. https://martinfowler.com/bliki/CanaryRelease.html  
- Martin Fowler. *Phoenix Server*. https://martinfowler.com/bliki/PhoenixServer.html  
- Martin Fowler. *Immutable Server*. https://martinfowler.com/bliki/ImmutableServer.html  
- Wikipedia. *Hypervisor*. https://en.wikipedia.org/wiki/Hypervisor  
- Wikipedia. *Docker (software)*. https://en.wikipedia.org/wiki/Docker_(software)  
- GeeksforGeeks. *Difference between Full Virtualization and Paravirtualization*. https://www.geeksforgeeks.org/difference-between-full-virtualization-and-paravirtualization/  
- GeeksforGeeks. *Architecture of Docker*. https://www.geeksforgeeks.org/architecture-of-docker/  
- Red Hat. *IaaS vs PaaS vs SaaS*. https://www.redhat.com/en/topics/cloud-computing/iaas-vs-paas-vs-saas  
- Invensis Learning. *Infrastructure as Code Tutorial*. https://www.invensislearning.com/blog/infrastructure-as-a-code-tutorial/  
- Codecademy. *Infrastructure configuration*. https://www.codecademy.com/article/infrastructure-configuration  
- Futurice. *Terraform examples*: AWS EC2 + Docker host. https://github.com/futurice/terraform-examples/tree/master/aws/aws_ec2_ebs_docker_host

*Remarques :* certains exemples (Dockerfile, Ansible, Terraform) sont **reformulés** et **simplifiés** pour un usage pédagogique; remplacez les identifiants/AMIs et chemins par ceux de votre environnement. Les figures décrivent les schémas vus en cours et ne contiennent pas d’images.
