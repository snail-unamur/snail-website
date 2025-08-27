---
title: Partie 2 – Devenir un·e power user
date: '2025-08-23'
type: book
weight: 20
summary: Deuxième séance, il est temps de voir comment utiliser un ordinateur comme un·e pro, via un terminal de commande. 😎
---

{{< toc hide_on="xl" >}}

Deuxième séance, il est temps de voir comment utiliser un ordinateur comme un·e pro, via un terminal de commande. 😎

[Les slides de la séance sont disponibles ici.](INFOB000-Cours-prepa-session02.pdf)

Quelques commandes de base pour vous en sortir:

- `pwd` (*print working directory*) permet d'afficher le répertoire dans lequel tu te trouves (aussi appelé le *répertoire courant*).
- `cd [directory]` (*change directory*) permet de changer de répertoire courant. Si aucun `directory` n'est précisé, la commande utilise le répertoire par défaut `~`. Il s'agit du *home directory* de l'utilisateur (`/home/`*userid*`/` sous Linux et MacOS).
- `man [command]` (*manual*) permet d'afficher la page de manuel relative à la commande donnée. Très utile, cette commande te permet de rapidement voir comment taper une commande ou comprendre ses différentes options. Utilise la touche `q` pour quitter le manuel.
- `ls [directory]` (*list*) permet de lister le contenu d'un répertoire donné. Si aucun répertoire n'est donné, la commande utilise le répertoire courant (`.`).

*Pro tip : la section 2 du manuel (`man 2 [function]`) est consacrée aux fonctions système, très utile à savoir pour un TP de système d'exploitation. Des exemples d'utilisation sont en général disponibles en bas de la page du manuel.* 😉

### Activité Jeu de piste en ligne de commande

Télécharge le fichier suivant [tresor_chateau.zip](tresor_chateau.zip) et dézipe le dans ton dossier utilisateur (`/home/tonidentifiant/`). Si tu veux le faire sans utiliser la souris, ouvre un terminal de commande et tape les commandes suivantes pour télécharger le fichier sur ta machine depuis le site web :

```bash
cd
wget https://snail.info.unamur.be/course/infoprepa/partie02/tresor_chateau.zip
```

La commande `ls` devrait normalement faire apparaître le fichier `tresor_chateau.zip` dans la liste des fichiers. Tu peux maintenant déziper le fichier à l'aide de la commande suivante :

```bash
unzip tresor_chateau.zip
```

La commande `ls` devrait maintenant faire apparaître le dossier `tresor_chateau`. Rends toi dans ce dossier et tape les commandes suivantes pour initialiser le jeu :

```bash
cd tresor_chateau
bash permissions.sh
```

Enfin, pour démarrer le jeu, lis le premier indice à l'aide des commandes suivantes :

```bash
cat panneau01.txt
```

*Pro tip : dans un terminal de commande, la [touche de tabulation](https://fr.wikipedia.org/wiki/Touche_de_tabulation) permet de compléter automatiquement la fin de la commande. Par exemple, `cd tres` + tabulation complétera la commande en `cd tresor_chateau`, pour autant qu'aucun autre dossier commençant par `tres` se trouve dans le répertoire courant.*

(adapté depuis [Le trésor du chateau: Jeu de piste en ligne de commande sous Linux](https://www.enseignons.be/preparation/86760/) de Cédric Libert)
