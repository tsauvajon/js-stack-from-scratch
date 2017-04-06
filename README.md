# JavaScript Stack from Scratch - FR

[![Build Status](https://travis-ci.org/verekia/js-stack-from-scratch.svg?branch=master)](https://travis-ci.org/verekia/js-stack-from-scratch)
[![Release](https://img.shields.io/github/release/verekia/js-stack-from-scratch.svg?style=flat-square)](https://github.com/verekia/js-stack-from-scratch/releases)
[![Dependencies](https://img.shields.io/david/verekia/js-stack-boilerplate.svg?style=flat-square)](https://david-dm.org/verekia/js-stack-boilerplate)
[![Dev Dependencies](https://img.shields.io/david/dev/verekia/js-stack-boilerplate.svg?style=flat-square)](https://david-dm.org/verekia/js-stack-boilerplate?type=dev)
[![Gitter](https://img.shields.io/gitter/room/js-stack-from-scratch/Lobby.svg?style=flat-square)](https://gitter.im/js-stack-from-scratch/)

[![React](/img/react-padded-90.png)](https://facebook.github.io/react/)
[![Redux](/img/redux-padded-90.png)](http://redux.js.org/)
[![React Router](/img/react-router-padded-90.png)](https://github.com/ReactTraining/react-router)
[![Flow](/img/flow-padded-90.png)](https://flowtype.org/)
[![ESLint](/img/eslint-padded-90.png)](http://eslint.org/)
[![Jest](/img/jest-padded-90.png)](https://facebook.github.io/jest/)
[![Yarn](/img/yarn-padded-90.png)](https://yarnpkg.com/)
[![Webpack](/img/webpack-padded-90.png)](https://webpack.github.io/)
[![Bootstrap](/img/bootstrap-padded-90.png)](http://getbootstrap.com/)

Bienvenue dans mon didacticiel moderne pour la pile JavaScript: **JavaScript Stack from Scratch**. ["EN FRANCAIS !"]
> **La version originale de ce didacticiel est disponible [en anglais](https://github.com/verekia/js-stack-from-scratch/), nous tâcherons de maintenir au mieux à jour la traduction au travers des évolutions à venir**

> 🎉 **Ceci est la version V2 de ce didacticiel, des changements majeurs sont apparus depuis la version 2016. Vérifiez le [Log de suivi des changement](/CHANGELOG.md)!**

Il s'agit d'un guide direct pour le montage d'une pile JavaScript. Il nécessite une certaine connaissance de programmation générale et des bases de JavaScript. **Il se concentre sur les outils d'interconnexion entre technologies** et vous fournis l' **exemple le plus simple possible** pour chaque outil. Vous pouvez voir ce didacticiel comme *un moyen d'écrire votre propre modèle à partir de zéro*. Étant donné que le but de ce didacticiel est de rassembler divers outils, je n'entre pas dans les détails sur la façon dont ces outils fonctionnent individuellement. Reportez-vous à leur documentation ou trouvez d'autres didacticiels si vous souhaitez acquérir une connaissance plus approfondie de chacun d'eux.

Vous n'avez pas besoin d'utiliser cette pile entière si vous construisez une page Web simple avec quelques interactions JS bien sûr (une combinaison de Browserify / Webpack + Babel + jQuery est suffisante pour pouvoir écrire le code ES6 dans différents fichiers), mais si vous voulez construire une application Web qui évolue, et que vous avez besoin d'aide pour configurer les choses, ce didacticiel fonctionnera très bien pour vous.

Un gros morceau de la pile décrit dans ce didacticiel utilise React. Si vous commencez et que vous voulez juste apprendre React, [create-react-app](https://github.com/facebookincubator/create-react-app) vous mettra en route avec un environnement React très rapidement et avec une pré-configuration. Je recommanderais par exemple cette approche à quelqu'un qui arrive dans une équipe qui utilise React et a besoin de rattraper au travers d'un terrain de jeu d'apprentissage. Dans ce didacticiel, vous n'utiliserez pas de configuration pré-faite, car je veux que vous compreniez tout ce qui se passe sous le capot.

Des exemples de code sont disponibles pour chaque chapitre, et vous pouvez tous les exécuter avec `yarn && yarn start`. Cependant je recommande d'écrire tout à partir de zéro vous-même en suivant les **instructions étape-par-étape**.

Le code final est disponible dans le [Référentiel JS-Stack-Boilerplate](https://github.com/verekia/js-stack-boilerplate), et dans le [releases](https://github.com/verekia/js-Stack-from-scratch/releases). Il existe également une [démonstration en ligne](https://js-stack.herokuapp.com/).

Fonctionne sous Linux, macOS et Windows.

## Table des matières

[01 - Node, Yarn, `package.json`](/tutorial/01-node-yarn-package-json.md#readme)

[02 - Babel, ES6, ESLint, Flow, Jest, Husky](/tutorial/02-babel-es6-eslint-flow-jest-husky.md#readme)

[03 - Express, Nodemon, PM2](/tutorial/03-express-nodemon-pm2.md#readme)

[04 - Webpack, React, HMR](/tutorial/04-webpack-react-hmr.md#readme)

[05 - Redux, Immutable, Fetch](/tutorial/05-redux-immutable-fetch.md#readme)

[06 - React Router, Server-Side Rendering, Helmet](/tutorial/06-react-router-ssr-helmet.md#readme)

[07 - Socket.IO](/tutorial/07-socket-io.md#readme)

[08 - Bootstrap, JSS](/tutorial/08-bootstrap-jss.md#readme)

[09 - Travis, Coveralls, Heroku](/tutorial/09-travis-coveralls-heroku.md#readme)

## À suivre

Configuration de votre éditeur (Atom en premier), MongoDB, Progressive Web App.

## Traductions

Si vous souhaitez ajouter votre traduction, veuillez lire les [recommandations de traduction](/how-to-translate.md) pour commencer!

### V2

#### Etat de la traduction :

les fichiers marqués par une "*" ne seront pas traduits, ni le fichiers contenant du code"
##### FAIT
"/"
- /.github*
- /img*
- README.me
- how-to-translate.md
- .gitignore*
- .travis.yml*
- mdlint.js*
- package.json*
- yarn.lock*
- /tutorial
  - 01-node-yarn-package-json.md

##### EN COURS
- CHANGELOG.md
- LICENSE.md

##### A FAIRE
- /tutorial
  - 02-babel-es6-eslint-flow-jest-husky.md
  - 03-express-nodemon-pm2.md
  - 04-webpack-react-hmr.md
  - 05-redux-immutable-fetch.md
  - 06-react-router-ssr-helmet.md
  - 07-socket-io.md
  - 08-bootstrap-jss.md
  - 09-travis-coveralls-heroku.md

Votre lien ici bientôt ;)

Consultez les [traductions en cours](https://github.com/verekia/js-stack-from-scratch/issues/147).

### V1

- [中文](https://github.com/pd4d10/js-stack-from-scratch) par [@pd4d10](http://github.com/pd4d10)
- [Italiano](https://github.com/fbertone/js-stack-from-scratch) par [Fabrizio Bertone](https://github.com/fbertone)
- [日本語](https://github.com/takahashim/js-stack-from-scratch) par [@takahashim](https://github.com/takahashim)
- [Русский](https://github.com/UsulPro/js-stack-from-scratch) par [React Theming](https://github.com/sm-react/react-theming)
- [ไทย](https://github.com/MicroBenz/js-stack-from-scratch) par [MicroBenz](https://github.com/MicroBenz)

## Crédits

Créé par [@verekia](https://twitter.com/verekia) – [verekia.com](http://verekia.com/).
Traduit en Français (en cours) par [@AmauryVanEspen](https://github.com/AmauryVanEspen/).


Licence: MIT
