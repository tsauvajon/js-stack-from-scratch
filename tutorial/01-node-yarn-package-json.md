# 01 - Node, Yarn, et `package.json`

Code disponible pour ce chapitre [ici](https://github.com/AmauryVanEspen/js-stack-walkthrough/tree/master/01-node-yarn-package-json).

Dans cette section, nous configurons Node, Yarn, un fichier `package.json` basique et essayons un package.

## Node

> 💡 **[Node.js](https://nodejs.org/)** est un environnement d'exécution JavaScript. Il est principalement utilisé pour le développement Back-End, mais aussi pour les scripts généraux. Dans le contexte du développement de Front-End, il peut être utilisé pour exécuter tout un tas de tâches telles que lintage, test et assemblage de fichiers.

Nous utiliserons Node pour tout dans ce tutoriel, donc vous en aurez besoin. Rendez vous sur la [page de téléchargement](https://nodejs.org/en/download/current/) pour **macOS** ou binaires **Windows**, ou sur la [page des installations du gestionnaire de paquets](https://nodejs.org/en/download/package-manager/) pour les distributions Linux.

Par exemple, sur **Ubuntu / Debian**, vous exécuteriez les commandes suivantes pour installer Node :

```sh
curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
sudo apt-get install -y nodejs
```

Vous voulez une version de Node > 6.5.0.

## Outils de gestion de la version de Node
Si vous avez besoin de la flexibilité pour utiliser plusieurs versions de Node, consultez [NVM](https://github.com/creationix/nvm) ou [tj/n](https://github.com/tj/n).

## NPM

NPM est le gestionnaire de paquets par défaut pour Node. Il est installé automatiquement avec Node. Les gestionnaires de paquets sont utilisés pour installer et gérer des paquets (modules de code que vous ou quelqu'un d'autre a écrit). Nous allons utiliser beaucoup de paquets dans ce didacticiel, mais nous utiliserons Yarn, un autre gestionnaire de paquetages.

## Yarn

> 💡 **[Yarn](https://yarnpkg.com/)** Node.js est un gestionnaire de paquets qui est beaucoup plus rapide que NPM, a un support hors-ligne et récupère des dépendances [plus prévisiblement](https://yarnpkg.com/en/docs/yarn-lock).

Depuis sa [sortie](https://code.facebook.com/posts/1840075619545360) en octobre 2016, il a reçu une adoption très rapide et pourrait bientôt devenir le gestionnaire de paquets de choix de la communauté JavaScript. Si vous souhaitez adhérer à NPM, vous pouvez simplement remplacer toutes les instructions `yarn add` et `thread-add -dev` de ce tutoriel par `npm install --save` et `npm install --save-dev`.

Installez Yarn en suivant les [instructions](https://yarnpkg.com/en/docs/install) pour votre système d'exploitation. Je vous recommande d'utiliser le **Script d'installation** à partir de l'onglet *Alternatives* si vous êtes sur MacOS ou Unix, pour [éviter](https://github.com/yarnpkg/yarn/issues/1505) en utilisant un autre gestionnaire de paquets :

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

## `package.json`

> 💡 **[package.json](https://yarnpkg.com/en/docs/package-json)** est le fichier utilisé pour décrire et configurer votre projet JavaScript. Il contient des informations générales (le nom de votre projet, la version, les contributeurs, la licence, etc.), les options de configuration pour les outils que vous utilisez, et même une section pour exécuter des *tâches*.

- Créez un nouveau dossier de travail, et entrez dedans avec `cd`.
- Exécutez `yarn init` et répondez aux questions (`yarn init -y` pour ignorer toutes les questions), pour générer automatiquement un fichier` package.json`.

Voici le `package.json` de base que je vais utiliser dans ce tutoriel:

```json
{
  "name": "your-project",
  "version": "1.0.0",
  "license": "MIT"
}
```

## Hello World

Créez un fichier `index.js` contenant` console.log ('Hello world')`

🏁 Exécutez `node .` dans ce répertoire (`index.js`est le fichier par défaut pour lequel Node recherche dans un dossier). Il devrait afficher "Hello world".

**Note**: Voyez-vous 🏁 drapeau de course emoji? Je l'utiliserai chaque fois que vous atteignez un **point de contrôle**. Nous allons parfois faire beaucoup de changements dans une rangée, et votre code peut ne pas fonctionner jusqu'à ce que vous atteigniez le prochain point de contrôle.

## `start` script

Exécuter `node .` pour exécuter notre programme est un peu trop bas niveau. Nous allons utiliser un script NPM / Yarn pour déclencher l'exécution de ce code à la place. Cela nous donnera une belle abstraction pour pouvoir toujours utiliser `yarn start`, même si notre programme devient plus compliqué.

- Dans `package.json`, ajoutez un objet `scripts` comme ceci:

```json
{
  "name": "your-project",
  "version": "1.0.0",
  "license": "MIT",
  "scripts": {
    "start": "node ."
  }
}
```

`Start` est le nom que nous donnons à la *tâche* qui exécutera notre programme. Nous allons créer beaucoup de tâches différentes dans cet objet `scripts` tout au long de ce tutoriel. `Start` est généralement le nom donné à la tâche par défaut d'une application. D'autres noms de tâches standard sont `stop` et `test`.

`package.json` doit être un fichier JSON valide, ce qui signifie que vous ne pouvez pas avoir de virgule finale. Faites attention lors de l'édition manuelle de votre fichier `package.json`. 🏁 Exécutez `yarn start`. Il devrait imprimer `Hello world`.

## Git et `.gitignore`

- Initialisez un dépôt Git avec `git init`

- Créez un fichier `.gitignore` et ajoutez-lui ce qui suit :

```gitignore
.DS_Store
/*.log
```

Les fichiers `.DS_Store` sont des fichiers macOS générés automatiquement que vous ne devriez jamais avoir dans votre dépôt. 

`npm-debug.log` et` yarn-error.log` sont des fichiers créés lorsque votre gestionnaire de paquets rencontre une erreur, nous ne voulons pas qu'ils soient versionnés dans notre dépôt.

## Installation et utilisation d'un paquet

Dans cette section, nous allons installer et utiliser un paquet. Un «paquet» est simplement un code que quelqu'un d'autre a écrit et que vous pouvez utiliser dans votre propre code. Cela peut être n'importe quoi. Ici, nous allons essayer un paquet qui vous aide à manipuler les couleurs par exemple. 

- Installez le paquet créé par la communauté appelé `color` en exécutant `yarn add color`

Ouvrez `package.json` pour voir comment Yarn a automatiquement ajouté 'color' dans `dependencies`.

Un dossier `node_modules` a été créé pour stocker le paquet.

- Ajoutez `node_modules/` à votre `.gitignore`

Vous remarquerez également qu'un fichier `yarn.lock` a été généré par Yarn. Vous devez 'commiter' ce fichier à votre dépôt, car cela garantira que tous les membres de votre équipe utilisent la même version de vos paquets. Si vous êtes en train de d'utiliser NPM au lieu de Yarn, l'équivalent de ce fichier est *shrinkwrap*.

- Ecrivez ce qui suit dans votre `index.js` :

```js
const color = require('color')

const redHexa = color({ r: 255, g: 0, b: 0 }).hex()

console.log(redHexa)
```

🏁 Exécutez `yarn start`. Il devrait afficher `#FF0000`.

Félicitations, vous avez installé et utilisé un paquet !

`color` est simplement utilisé dans cette section pour vous apprendre à utiliser un paquet simple. Nous n'en aurons plus besoin, donc vous pouvez le désinstaller :

- Exécutez `yarn remove color`

## Deux types de dépendances

Il existe deux types de dépendances de paquets, `"dependencies"` et `"devDependencies"`:

**Dependencies** sont les bibliothèques dont vous avez besoin pour que votre application fonctionne (React, Redux, Lodash, jQuery, etc.). Vous les installez avec `yarn add [package]`.

**Dev Dependencies** sont les bibliothèques utilisées pendant le développement ou pour créer votre application (Webpack, SASS, linters, frameworks de test, etc.). Vous les installez avec `yarn add --dev [package]`.

Prochaine section:[02 - Babel, ES6, ESLint, Flow, Jest, Husky](02-babel-es6-eslint-flow-jest-husky.md#readme)

Retour à la [table des matières](https://github.com/AmauryVanEspen/js-stack-from-scratch#table-of-contents).
