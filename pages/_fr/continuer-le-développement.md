---
layout: page
title: Continuer le développement
lang: fr
trans_url: Continuing development
---
L’outil de recherche des prestations est une application presque autonome, avec une intégration externe requise uniquement pour la fonctionnalité de rétroaction.



En raison des délais courts de lancement et d’itération sur ce produit, il y a eu des compromis sur plusieurs décisions de conception. Les calculs de prestations et la logique de routage sont [étroitement liés](https://en.wikipedia.org/wiki/Coupling_(computer_programming)) à l’application elle-même. Il est donc facile de mettre à jour le contenu existant, mais cela rend l’ajout de nouveaux itinéraires et prestations plus complexe.

### Référentiel

[C19-Benefits-Node](https://github.com/cds-snc/c19-benefits-node)

Référentiel principal pour l’outil de recherche des prestations

[C19-Benefits-Manifest](https://github.com/cds-snc/c19-benefits-manifest)

Journal d’audit des lancements en production

### À l’intention des développeurs

* Sommaire
* * Utilisation des services de tiers.
  * Tests automatisés.
  * Poursuite du développement.
* Développer et exécuter l’application.



### Sommaire

L’application de l’outil de recherche des prestations est une application express côté serveur utilisant le modèle [Nunjucks](https://mozilla.github.io/nunjucks/) sur le serveur et le cadre [Tailwind CSS](https://tailwindcss.com/) pour le style. L’échafaudage de l’application provient du générateur express.



L’application met en œuvre de nombreuses pratiques recommandées pour un service Web moderne.



* Elle suit les [directives de SNC](https://numerique.canada.ca/a11y/) pour l’élaboration de services inclusifs et accessibles.
* Elle dispose de diverses fonctionnalités de sécurité, comme les [en-têtes HTTP sécurisés](https://helmetjs.github.io/), la [protection CSRF](https://github.com/expressjs/csurf) et la validation de formulaire.
* Elle est abondamment testée, y compris des tests [cypress](https://www.cypress.io/) de bout en bout avec des [analyses d’accessibilité intégrées](https://github.com/avanslaars/cypress-axe).
* Elle comprend un pipeline d’intégration continue et de déploiement continu (IC/DC), compatible avec [GitHub Actions](https://github.com/features/actions).
* Elle peut s’exécuter en tant qu’application de nœud sur un système d’exploitation *nix ou Windows ou en tant que conteneur [Docker](https://docs.docker.com/install/).
* Elle comprend des [scripts terraform](https://github.com/cds-snc/c19-benefits-node/tree/master/terraform) pour le déploiement dans Azure.

### Utilisation des services de tiers

On utilise plusieurs services tiers pour un meilleur flux de développement et une sécurité continue.



* [GitHub](https://github.com/) est un service infonuagique qui stocke notre code source, suit les changements de code et facilite les révisions de code.
* [GitHub Actions](https://github.com/features/actions) est un service d’IC/DC qui nous permet de tester et de [déployer notre code](https://github.com/cds-snc/c19-benefits-node/blob/master/.github/workflows/build-deploy-dev.yml) directement à partir de GitHub.
* * Les services d’IC/DC abondent, mais on a utilisé GitHub Actions parce qu’il était facile à configurer, et avec sa configuration basée sur le yml, il serait aussi facile de partir.
* [Heroku](https://www.heroku.com/home) est une plateforme entièrement gérée en tant que service. Nous utilisons [Review Apps](https://devcenter.heroku.com/articles/github-integration-review-apps) de Heroku pour développer des applications jetables par demande d’extraction, ce qui facilite les examens de code.
* [Snyk](https://snyk.io/) est un logiciel comme service qui analyse nos dépendances liées aux trousses avec des problèmes connus. Il nous avertit lorsqu’une version d’une trousse que nous utilisons une exploitation connue.
* [LGTM](https://lgtm.com) est un logiciel comme service d’analyse de sécurité continue. Il analyse chaque demande d’extraction pour déterminer les vulnérabilités de sécurité possibles.
* [AirTable](https://airtable.com/) est une base de données comme service que l’on a utilisé pour saisir les commentaires des utilisateurs de l’application. L’interface conviviale d’AirTable a permis à nos chercheurs et concepteurs d’analyser facilement les commentaires des utilisateurs sans devoir élaborer une solution personnalisée.



### Tests automatisés

Toutes les nouvelles demandes d’extraction ont un ensemble de tests automatisés exécutés contre elles.



* [Jest](https://jestjs.io/) : Tests unitaires pour vérifier la bonne logique interne des composantes.
* [ESLint](https://eslint.org/) : application de lint JavaScript qui assure un protocole JS uniforme dans toute l’application.
* [Cypress](https://www.cypress.io/) : Tests de bout en bout axé sur les comportements qui passent par les flux utilisateur souhaités.
* * [cypress-axe](https://github.com/avanslaars/cypress-axe) : on effectue une analyse d’accessibilité par page (à l’aide d’axe) pour vérifier les violations dans le balisage.
* [ShellCheck](https://github.com/koalaman/shellcheck) : Un outil d’analyse statique au moyen duquel on exécute tous les scripts shell qui détecte les problèmes de syntaxe, les problèmes sémantiques et les pièges qui peuvent pousser un script à produire des messages d’erreur difficiles à comprendre, se comporter étrangement ou échouer dans certaines circonstances.
* [Jsonlint](https://github.com/zaach/jsonlint) : application de lint de notation d’objet JavaScript pour s’assurer que les fichiers locaux sont toujours valides.
* [Seekret](https://github.com/apuigsech/seekret) : Outil permettant de s’assurer que les secrets comme les mots de passe ou les clés API ne sont pas enregistrés dans le code source.

### Poursuite du développement

[Marche à suivre pour poursuivre le développement dans ce projet](https://docs.google.com/document/d/1JNiTEslQjt8xW7jXF--kAAeCH6uIGV12y4mAwwnitvM/edit#heading=h.2bn6wsx) : que votre objectif soit de restructurer le service dans une nouvelle technologie ou de développer et de publier ce code en particulier.



### Développer et exécuter l’application

Consultez [README](https://github.com/cds-snc/c19-benefits-node/blob/master/README.md) pour obtenir des instructions plus détaillées sur le développement et le déploiement de l’application.