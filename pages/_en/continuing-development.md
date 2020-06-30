---
layout: page
title: Continuing development
lang: en
trans_url: Continuer le développement
---
This document describes how to continue development with this codebase — as well as the app structure and the technologies used — to make it easy to revive this work in the future.

We foresee two scenarios for continuing development:

1. Run the app and view all the pages in order to rebuild it using other technology.
2. Continue development of this specific repository

## 1. Run the app and view all the pages

All you need to do here is run the app and then find all the URLs.

1. First, get it to boot up.

   * Check out “Running Locally” in the [README](https://github.com/cds-snc/c19-benefits-node/blob/master/README.md).
   * The app will be running at <http://localhost:3030/>.
2. A full list of URLs can be found in [/config/routes.config.js](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/config/routes.config.js). You will have to navigate the flows to see them all.

## 2. Continue using our repository

In order to pick up development after some arbitrary length of time, first you need to run the app, update all the npm dependencies, and then check that all the tests pass before doing anything else.

1. First, get it to boot up.

   * Check out “Running locally” in the [README](https://github.com/cds-snc/c19-benefits-node/blob/master/README.md).
   * The app will be running at <http://localhost:3030/>.
2. Second, run the tests. If they all pass (they should), then you can continue.

   * Check “Testing” in the [README](https://github.com/cds-snc/c19-benefits-node/blob/master/README.md).
3. Update all the dependencies, as many will be out of date.

### Repository structure

| Folder               | Purpose                                                                                          |
| -------------------- | ------------------------------------------------------------------------------------------------ |
| `/.github/workflows` | CI/CD pipelines/workflows                                                                        |
| `/bin`               | Runtime script for Node.js and helpful shell scripts                                             |
| `/config`            | Configurations for the npm modules<wbr>/middleware used                                          |
| `/cypress`           | End to end test fixtures and integrations                                                        |
| `/locales`           | Internationalization (i18n) keys to support both English and French official languages           |
| `/middleware`        | Custom written middleware                                                                        |
| `/public`            | Static resources (images, scripts, stylesheets, favicon): all our styling is in `/public/scss`.  |
| `/routes`            | Controllers (routes and business logic) and unit tests                                           |
| `/terraform`         | Azure and HashiCorp Terraform scripts for Infrastructure as Code (IaC)                           |
| `/utils`             | Utility functions and [express middleware](https://expressjs.com/en/guide/using-middleware.html) |
| `/views`             | [Pug](https://pugjs.org/api/getting-started.html) view files that translate to HMTL at runtime   |

### Technology Choices

#### Development

* Express.js (Node.js)
* Nunjucks (view technology).
* express-validator (form validation).
* Tailwind CSS (styles).
* Jest (unit tests).
* Cypress (end to end testing).
* Morgan (HTTP request logger middleware).
* Helmet (Content security policy middleware).

#### Continuous Integration & Delivery

* GitHub Actions.
* Seekret (find secrets in code).
* Snyk (continuous security analysis).
* Semmle/LGTM (continuous security analysis).

#### Cloud

Microsoft Azure is the Cloud Service Provider (CSP)

* Azure AppService (PaaS offering to deploy the app).
* Azure Container Registry.
* Azure KeyVault (Secrets).
* Azure Application Insights (Metrics and logging).

#### Deployment

* Azure AppService.
* Docker.

If you have any questions or feedback about the product, please email the [Canadian Digital Service](mailto:cds-snc@tbs-sct.gc.ca).