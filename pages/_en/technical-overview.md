---
layout: page
title: Technical overview
lang: en
trans_url: Aperçu technique
childPages:
  - Continuing development
---
The benefit finder is an almost stand-alone application, with outside integration required for feedback functionality only.



Due to short timelines to launch and iterate on this product, there were compromises on several design decisions. The benefit calculations and routing logic are [tightly coupled](https://en.wikipedia.org/wiki/Coupling_(computer_programming)) to the application itself. This makes it easy to update existing content, but introduces complexity when adding new benefits and routes.

### Repository

[C19-Benefits-Node](https://github.com/cds-snc/c19-benefits-node)

Main repository for the benefit finder

[C19- Benefits-Manifest](https://github.com/cds-snc/c19-benefits-manifest)

Audit log for releases to production

### For developers

* Summary

  * Use of third-party services.
  * Automated tests.
  * Continuing development.
* Build and run the application.



### Summary

The benefit finder application is a server-side express application using [Nunjucks](https://mozilla.github.io/nunjucks/) templating on the server and the [Tailwind CSS](https://tailwindcss.com/) framework for styling. The application scaffolding comes from the express generator.



The application implements many recommended practices for a modern web service.



* It follows [CDS guidelines](https://digital.canada.ca/a11y/) for building inclusive and accessible services.
* It has various security features, such as [security-minded HTTP headers](https://helmetjs.github.io/), [CSRF protection](https://github.com/expressjs/csurf), and form validation.
* It is copiously tested, including end-to-end [cypress](https://www.cypress.io/) tests with [integrated accessibility scans](https://github.com/avanslaars/cypress-axe).
* It includes a Continuous integration and deployment (CI/CD) pipeline, compatible with [GitHub Actions](https://github.com/features/actions).
* It can run as a node app on a *nix or Windows OS or as a [Docker](https://docs.docker.com/install/) container.
* It includes [terraform scripts](https://github.com/cds-snc/c19-benefits-node/tree/master/terraform) for deploying to Azure.

### Use of third-party services

We use several third-party services for an improved development workflow and continuous security.



* [GitHub](https://github.com/) is a cloud-based service that stores our source code, tracks code changes and facilitates code reviews.
* [GitHub Actions](https://github.com/features/actions) is a Continuous integration and deployment (CI/CD) service that allows us to test and [deploy our code](https://github.com/cds-snc/c19-benefits-node/blob/master/.github/workflows/build-deploy-dev.yml) right from GitHub.

  * CI/CD services abound, but we used GitHub Actions because it was easy to set up, and with its yml-based configuration it would also be easy to leave..
* [Heroku](https://www.heroku.com/home) is a fully-managed platform as a service. We use Heroku [Review Apps](https://devcenter.heroku.com/articles/github-integration-review-apps) to build disposable applications per pull request, facilitating code reviews.
* [Snyk](https://snyk.io/) is a software as a service product that scans through our dependencies for packages with known issues. It alerts us when a version of a package we’re using has a known exploit.
* [LGTM](https://lgtm.com) is a software as a service product for continuous security analysis. It analyzes each pull request for potential security vulnerabilities.
* [Airtable](https://airtable.com/) is a database as a service product that we used to capture feedback from users of the application. Airtable’s user friendly interface allowed our researchers and designers to easily analyze user feedback without having to build a custom solution.



### Automated tests

All new pull requests have a suite of automated tests run against them.



* [Jest](https://jestjs.io/): Unit tests to verify correct internal logic for components.
* [ESLint](https://eslint.org/): JavaScript linter that ensures uniform JS throughout the app.
* [Cypress](https://www.cypress.io/): End-to-end behaviour-driven tests that run through desired user flows.

  * [cypress-axe](https://github.com/avanslaars/cypress-axe): We run an accessibility scan per page (using axe) to check for violations in the markup.
* [ShellCheck](https://github.com/koalaman/shellcheck): A static analysis tool that we run all of our shell scripts through that detects syntax issues, semantic problems and pitfalls that may cause a script to produce cryptic error messages, behave strangely or fail under certain circumstances.
* [Jsonlint](https://github.com/zaach/jsonlint): JavaScript object notation linter to ensure Locale files are always valid.
* [Seekret](https://github.com/apuigsech/seekret): A tool to ensure that secrets such as passwords or API keys do not get checked into source code.

### Continuing development

[A walkthrough on how to continue development on this project](/continuing-development/): whether your aim is to rebuild the service in a new technology or to develop and release this codebase specifically.



### Build and run the application

Check out the [README](https://github.com/cds-snc/c19-benefits-node/blob/master/README.md) for more detailed instructions on building and deploying the application.