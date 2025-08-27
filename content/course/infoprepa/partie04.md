---
title: Partie 4 – Devenir un·e développeur·euse
date: '2025-08-23'
type: book
weight: 40
summary: Dernière séance, pour se familiariser avec l'environnement de développement intégré (EDI) Visual Studio Code. 🛠️
---

{{< toc hide_on="xl" >}}

Dernière séance, pour se familiariser avec l'environnement de développement intégré (EDI) [Visual Studio Code](https://code.visualstudio.com), utilisé en première année, on te propose de suivre un mini tutoriel pour te présenter quelques fonctionnalités de base. Tu te rendras vite compte que les EDIs sont des outils puissants, personnalisables à volonté. N'hésites donc pas à explorer par toi même et voir ce qu'il est possible de faire avec.

[Les slides de la séance sont disponibles ici.](INFOB000-Cours-prepa-session04.pdf)

### Les bases

La première étape lorsque l'on veut programmer en Python est d'installer le plugin Python via le panneau *Extensions*. L'installation du plugin Python devrait également déclencher l'installation du plugin Python Debugger :

![Ouvrir le panneau d'extension et installer le plugin Python](vscode01-python-extension.gif)

Une fois le plugin installé, tu peux revenir à l'explorateur pour ouvrir un dossier dans lequel on va placer les fichiers `.py` (ou via le menu `Fichier` -> `Ouvrir le dossier...`).  On te conseille vivement de commencer par là afin de ne pas perdre des fichiers dans les différents coins du disque dur de ta machine.

![Ouvrir un dossier ](vscode02-ouvrirdossier.gif)

Il est maintenant temps de créer un premier fichier avec l'extension `.py` via un clic droit dans l'explorateur -> `Nouveau fichier...`. N'oublie pas que le nom du fichier doit se terminer par `.py` pour indiquer à ta machine qu'il s'agit d'un fichier Python.

![Nouveau Fichier](vscode03-nouveaufichier.gif)

Écrivons maintenant un premier programme qui affichera le message `Hello World!` dans le terminal et exécutons le. Tu peux copier et coller le code suivant dans le fichier que tu viens de créer :

```python
print("Hello World!")
```

Une fois fait, n'oublie pas de sauver le fichier (`CTRL` + `s` sur Windows et Linux ou `Command` + `s` sur Mac). Tu peux maintenant lancer l'interpréteur Python pour qu'il exécute ton fichier, soit via le bouton play en haut à droite de la fenêtre, soit en faisant un clic droit sur ton fichier -> `Exécuter le fichier Python dans le terminal`.

![Nouveau Fichier](vscode04-executer.gif)

### Renommer une variable et naviguer dans le code

Pour la suite, tu vas avoir besoin de créer un nouveau fichier (par exemple, `deviner.py`) et d'y ajouter le code suivant :

```python
import random

# Générer un nombre aléatoire entre 1 et 100
d = random.randint(1, 100)
f = False

print("Bienvenue dans le jeu de devinette!")
print("J'ai choisi un nombre entre 1 et 100. Pouvez-vous le deviner?")

while not f:
    # Demander à l'utilisateur de saisir un nombre
    n = int(input("Entrez votre nombre: "))
    
    if n < d:
        print("C'est plus grand!")
    elif n > d:
        print("C'est plus petit!")
    else:
        print(f"Bravo! Vous avez deviné le nombre {d}.")
        f = True
```

On te laisse le soin de deviner ce que fait ce bout de code. 😁 Comme tu peux le voir, les noms de variables ne sont pas très explicites. Une bonne pratique lorsque l'on programme consiste à donner des noms qui peuvent renseigner un autre programmeur lisant le code sur ce que cette variable représente. Par exemple, la variable `d` est la valeur aléatoire comprise entre 1 et 100 que l'utilisateur doit deviner. Heureusement, les EDIs permettent de renommer facilement une variable. Pour cela, il te suffit de sélectionner la variable à un endroit de ton code, clic droit -> `Renommer le symbole`.

![Renommer une variable](vscode05-renommer.gif)

Une fois renommé, tu remarqueras que l'EDI a pris soin pour toi d'utiliser le même nom aux différents endroits où le symbole apparaît. On te laisse le soin de renommer les autres variables avec des noms plus adéquats. La fonction de renommage est souvent utilisée par les développeurs, que ce soit pour renommer des variables, des modules, des fonctions, etc.

Afin de comprendre ce que fait une variable et de lui donner un meilleur nom, il est parfois nécessaire de voir comment la variable a été définie (on parle aussi de déclaration de variable) et utilisée dans le code. Un EDI permet de naviguer facilement dans un code source de différentes manières. Par exemple, pour aller à la déclaration d'une variable, il te suffit de faire un clic droit -> `Atteindre la définition`.

![Naviguer vers la définition d'une variable](vscode06-gotodefinition.gif)

Cette fonctionnalité est très pratique lorsque l'on a un code source important et qu'il n'est pas clair où une variable est définie pour la première fois. L'EDI permet également de naviguer vers les différents endroits où une variable est utilisée, ce qui est pratique pour comprendre à quoi celle-ci sert dans le code. Pour cela, il suffit de clic droit sur la variable -> `Atteindre les références` pour ouvrir une fenêtre dans l'éditeur reprenant les endroits où la variable est utilisée et/ou modifiée.

![Naviguer vers les références d'une variable](vscode07-gotoreferences.gif)

### Extraire une fonction

Contrairement à ce que tu pourrait croire, écrire un morceau de code (qui fera partie d'un programme) ne se fait pas en une fois. En général, on écrit une première version du code que l'on va retravailler pour diverses raisons : améliorer sa lisibilité, optimiser son exécution ou encore regrouper les bouts de code similaires, voire identiques dans une fonction (il s'agit de *modulariser* le code). C'est ce que l'on appelle communément du *refactoring* de code (ou *refactorisation* en français). Pour améliorer la lisibilité, nous venons de voir comment, par exemple, renommer une variable. Ton EDI te permet d'aller plus loin, par exemple, en extrayant une fonction d'un morceau de code existant. Pour cela, il faut sélectionner le morceau de code en question, cliquer sur la petite ampoule qui apparaît 💡 -> `Méthode d'extraction`.

![Extraire une fonction depuis un morceau de code existant](vscode08-extractionfonction.gif)

Une fois extraite, tu peux rendre la fonction plus modulaire en ajoutant, par exemple, un paramètre.

![Ajouter un paramètre à une fonction](vscode09-ajoutparametre.gif)

La fonction d'auto complétion de l'EDI te facilitera la vie en te proposant différentes options. Dans ce cas-ci, le paramètre `valeur_max` qui vient d'être déclaré dans l'entête de la fonction (`def deviner_nombre(valeur_max)`).

### Poser un diagnostic en cas d'erreur

En cas d'erreur lors de l'exécution d'un programme Python, l'interpréteur donnera quelques indications. Si tu exécutes le programme de la vidéo précédente, l'interpréteur provoquera une erreur avec le message suivant : `deviner_nombre() missing 1 required positional argument: 'valeur_max'`. Celui ci nous dit qu'il manque un argument lors de l'appel à `deviner_nombre()`. Les messages d'erreur peuvent paraître assez cryptiques au début, mais renseignent en général assez bien sur ce qui ne va pas. N'hésite jamais à le traduire en français si l'anglais n'est pas (encore ;-)) ton point fort ou à copier et coller le message d'erreur dans ton moteur de recherche préféré pour avoir plus d'information.

![Navigation vers la localisation probable en cas d'erreur](vscode10-navigationerreur.gif)

Un autre élément intéressant du message d'erreur est la localisation (probable) de cette erreur : `File: "/Users/.../deviner.py", line 23, in <module> deviner_nombre()`. En passant ta souris sur <u>`"/Users/.../deviner.py", line 23`</u>, ton EDI t'indiques que tu peux te rendre à l'endroit renseigné (via `cmd` + clic sur Mac), ce qui facilite le diagnostic et la correction de l'erreur. Dans ce cas ci, il suffit simplement d'ajouter une valeur lors de l'appel à `deviner_nombre()`. Par exemple, `deviner_nombre(100)` fera deviner un nombre entre 1 et 100 à l'utilisateur.

### Documenter le code

Lorsque l'on programme, il est important de documenter son code. Tu as sans doute remarqué les commentaires précédés d'un dièse `#` dans le code que nous t'avons fourni plus haut. Ces commentaires renseignent sur les différentes étapes du code, par exemple lors de l'appel à une fonction externe comme `randint`. Ces commentaires sont ignorés par l'interpréteur Python. Autrement dit, si tu veux qu'une ligne de code ne soit pas exécutée sans pour autant la supprimer, ajouter un dièse `#` au début de la ligne et l'interpréteur l'ignorera.

Maintenant, si tu passes le curseur de ta souris sur `randint`, l'EDI t'affichera une fenêtre reprenant l'entête de la fonction, ainsi qu'une phrase décrivant ce que fait cette fonction :

```python
(variable) def randint(
    a: int,
    b: int
) -> int
Return random integer in range [a, b], including both end points.
```

Voyons comment faire pour documenter la fonction `deviner_nombre` que l'on vient de définir. Tout d'abord, on va installer le plugin [*autoDocstring*](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring) qui permet de générer une "*Docstring*". Il s'agit d'une chaîne de caractères spéciale (comprise entre `"""` et `"""`) avec la documentation de la fonction. Il existe plusieurs formats de docstring. Dans notre cas, nous utiliserons le format `numpy`, qui est à renseigné dans les paramètres de l'extension.

![Installer le plugin autoDocstring](vscode11-installationautodocstring.gif)

Une fois le plugin installé et configuré, tu peux revenir dans le code et positionner ton curseur à la ligne en dessous de la fonction `deviner_nombre`. En tapant `"""`, tu vas voir l'autocompletion te proposer la génération d'un docstring au format `numpy`. Il ne te reste alors qu'à compléter la documentation en renseignant les informations pour les différents champs indiqués.

![Génération de la docstring](vscode12-generationdocstring.gif)

Si tu passes ta souris sur la fonction `deviner_nombre`, tu devrais maintenant voir apparaître la documentation :

```python
(function) def deviner_nombre(valeur_max: Any) -> None
Fonction qui fait deviner un nombre entre 1 et valeur_max.

Parameters
   valeur_max : int
   La valeur maximale que peut prendre le nombre à faire deviner.
```

### Afficher l'historique des modifications

Bon, après toutes ces modifications, il te sera parfois nécessaire de devoir revenir en arrière (ou simplement de voir ce qui a changé dans le fichier). Là encore, l'EDI peut t'aider. Il est pourvu d'un mécanisme local permettant d'enregistrer des versions intermédiaires d'un fichier. Pour cela, rien de plus facile, clic droit sur un fichier -> `Ouvrir la chronologie` pour afficher une liste des versions précédentes. En cliquant sur une version, l'EDI ouvrira une fenêtre permettant de comparer la version courante à cette version précédente.

![Ouvrir l'historique local d'un fichier](vscode13-historiquelocal.gif)

Ce mécanisme bien pratique a toutefois un gros désavantage : il est local. Ce qui veut dire que si tu déplaces ou renomme le fichier, il est perdu. Tu ne peux pas non plus envoyer le fichier avec son historique à quelqu'un d'autre ou collaborer à plusieurs sur le même fichier.

Pour cela, tu vas avoir besoin d'un autre outil : [Git](https://git-scm.com), un système de gestion de versions. 😉

### Éviter les erreurs avec un linter

Un quoi ? Un *linter*, c'est le nom donné aux outils d'analyse de code qui permettent de détecter des erreurs dans le code. Les erreurs peuvent aller de l'oubli d'un espace (pour que le code soit bien formaté) à des erreurs qui peuvent faire crasher le programme (comme plus haut). Il existe plein de linters différents et tu apprendras même à en écrire un en master. Mais pour le moment on va se contenter d'utiliser [Pylint](https://pylint.readthedocs.io/) et le [plugin VSCode](https://marketplace.visualstudio.com/items?itemName=ms-python.pylint) qui va avec.

Une fois le plugin installé, reviens à la version du code qui a provoqué une erreur via la chronologie des versions du fichier. Tu vas voir que ton EDI va maintenant souligner des bouts de code en différentes couleurs : bleu, jaune, rouge. Ces couleurs représentent le niveau de l'erreur pointée par Pylint (aussi appelé le *severity level*) : bleu pour les erreurs mineures, jaune pour des erreurs pouvant poser problème (*warnings*) et rouge pour les erreurs qui ne manqueront pas de provoquer un crash du programme (*errors*). Si tu passes ta souris sur les lignes concernées, tu verras un message te renseignant sur l'erreur relevée par le linter.

![Voir l'analyse de Pylint](vscode15-viewpylint.gif)

Comme tu peux le voir, la ligne où l'appel à `deviner_nombre()` se fait sans donner de valeur maximale entre les parenthèses est en rouge, indiquant une erreur qui va (comme on l'a vu) provoquer un crash. En passant ta souris sur la ligne, le message d'erreur suivant apparaît :

> No value for argument 'max_value' in function call Pylint([E1120:no-value-for-parameter](https://pylint.readthedocs.io/en/latest/user_guide/messages/error/no-value-for-parameter.html))

Le message proprement dit te renseigne sur l'erreur (ici, on a pas donné de valeur `max_value`), mais il contient aussi un lien vers une page web expliquant pourquoi Pylint considère que c'est une erreur. Ici, l'erreur `E1120:no-value-for-parameter` est utilisée lorsqu'un appel de fonction passe trop peu d'arguments.

Si tu as suivi nos instructions jusqu'ici, tu devrais voir d'autres erreurs mineures en bleu dans le code avec des messages signalant qu'une ou plusieurs lignes de code sont trop longues :

> Line too long (102/100) Pylint([C0301:line-too-long](https://pylint.readthedocs.io/en/latest/user_guide/messages/convention/line-too-long.html))

Ou encore qu'il y a des espaces en trop dans le code :

> Trailing whitespace Pylint([C0303:trailing-whitespace](https://pylint.readthedocs.io/en/latest/user_guide/messages/convention/trailing-whitespace.html))

Cela peut te paraître peu important. Après tout, le programme va tourner sans problème. Le souci, c'est que si le format n'est pas standard, cela va compliquer la lecture du code au bout d'un moment. Et en cas de travail de groupe, c'est pas une bonne chose. Imagine un syllabus où le prof passe son temps à changer de style : une fois en Arial 11 avec des numéros de chapitres arabes, une fois en Times 14 avec des numéros de chapitres romains, une fois en Comic Sans 12 avec des lettres comme numéros de chapitres, etc. Le contenu du syllabus est là, mais ton étude ne sera pas aussi simple que si le même style avait été utilisé pour l'ensemble du syllabus.

Un adage en informatique attribué à Martin Golding dit de "*toujours coder comme si le gars qui finit par maintenir ton code est un psychopathe violent qui sait où tu vis*." 😬 Autrement dit, utilise un style standard... mais on va te montrer comment automatiser ça (en partie).

### Formater son code automatiquement

Pour ça aussi il existe des plugins. Ici on va utiliser un [plugin](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter) pour un outils appelé [Black Formatter](https://black.readthedocs.io/) qui est, comme son nom l'indique, un outils de mise en forme le code.

Une fois que c'est fait, tu peux mettre le code en forme, soit en utilisant un clic droit -> `Mettre le document en forme`, soit en utilisant la barre de commande de l'EDI située en haut de la fenêtre. Là tu vas pouvoir taper des commandes en commençant par taper `>`. L'autocomplétion te proposera alors différentes commandes. Si tu tapes `> Mettre en forme`, tu devrais voir apparaître plusieurs propositions, dont `Mettre le document en forme`. Sélectionne la commande avec les flèches du clavier (⬆️ et ⬇️) et appui sur entrer (↩️) pour voir ton code se mettre en forme sous tes yeux ébahis. 😁

![Utiliser Black Formatter](vscode15-useformatter.gif)

*Pro tip : le raccourci `CTRL+p` (ou `Command+p` sur Mac) permet d'accéder à la barre de commande plus rapidement.*

Voilà, tu es prêt. Il ne te reste plus qu'à te familiariser avec les raccourcis clavier pour effectuer les différentes tâches que nous t'avons montrées ici. Cela te permettra de gagner un temps précieux lors de tes séances de programmation. 😉
