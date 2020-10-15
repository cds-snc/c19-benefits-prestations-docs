---
layout: page
title: Conception
lang: fr
trans_url: Design
---
La conception a été menée en s'appuyant sur les meilleures pratiques du domaine. La première itération reposait sur l’hypothèse que les utilisateurs doivent :

* naviguer facilement dans l’outil en ligne, en se concentrant sur une question à la fois;
* choisir dans une liste de situations apparentées rédigées en langage simple;
* accéder à une liste des prestations qui pourraient leur être offertes, ainsi qu’à des renseignements sur le montant de l’aide financière qui pourrait être disponible au moyen de chaque prestation;
* accéder directement aux renseignements ou formulaires de demande.

L’itération comprenait également un outil de rétroaction pour mieux comprendre les lacunes en matière de services et de politiques.

On a ensuite poursuivi les travaux en nous fondant sur les conclusions de la recherche, ce qui a entraîné de nombreux changements dans le contenu et la conception. Voici les points saillants de ces changements :

* La conception affiche maintenant l’option de crédit de la taxe sur les produits et services (TPS), indique aux gens comment vérifier s’ils reçoivent ce crédit et donne accès à de plus amples renseignements sur la TPS.
* L’outil utilise le mot « revenu » au lieu de « travail » (par exemple, « perte de revenu ») parce que les participants à la recherche ont indiqué que la date à laquelle ils ont perdu leur travail différait souvent de la date à laquelle ils ont perdu leur revenu.
* On a insisté sur le fait que l’outil de recherche des prestations permet aux gens de faire une demande pour la PCU, comme l’indiquent les rapports médiatiques. Pour faciliter cette tâche, nous avons demandé aux personnes qui étaient admissibles à l’AE et à la PCU de « Présenter une demande de PCU », au lieu de « Présenter une demande d’AE et de PCU ».
* La conception en haut de la page des résultats indique le nombre de prestations disponibles. Dans les itérations précédentes, la recherche a indiqué que les gens n’examinaient que la première option et n’avaient pas remarqué d’autres options ci-dessous.
* Le terme « dette étudiante » était ambigu, donc la question a été changée en « Avez-vous des prêts étudiants que vous devez au gouvernement? » au lieu de « Avez-vous des dettes étudiantes? »
* Un texte a été ajouté aux pages d’introduction et de résultats pour préciser que l’outil ne garantit pas l’admissibilité, mais fournit plutôt une liste des prestations possibles pour lesquelles les gens peuvent présenter une demande.
* On a ajouté « Aucune des options ci-dessus » à titre provisoire afin que les personnes recevant des prestations d’invalidité puissent répondre aux autres questions et accéder à une page de résultats.
* Le contenu « Canadiens à l’étranger » figurant sur la page d’accueil a été déplacé à un endroit moins visible sur la page, puisque dans les premières itérations, certains croyaient que l’outil de recherche des prestations était destiné aux Canadiens à l’étranger. Ce lien a finalement été supprimé de la page d’accueil.
* Le contenu a été modifié et ajouté pour aider les travailleurs indépendants à naviguer dans le service.
* On a également modifié la page des résultats de façon à ce qu’en plus de connaître les prestations auxquelles ils pourraient être admissibles, les utilisateurs connaissent aussi les prestations qu’ils n’ont pas le droit de recevoir. Cela permet aux gens de bien comprendre le paysage des prestations et de connaître les prestations qui sont actuellement intégrées à l’outil.

## Examens d’accessibilité

Deux examens d’accessibilité ont été effectués pour ce produit : l’une par un expert en accessibilité de SNC et l’autre par la Direction générale de l’innovation, de l’information, de la technologie, et des services aux citoyens d’EDSC. Voici quelques-uns des problèmes d’accessibilité qui ont été abordés, soit par voie d’examen, soit par itération de conception :

* Ajouter un titre distinct à chaque page pour aider les lecteurs d’écran à naviguer rapidement d’une page à l’autre.
* S’assurer que chaque lien s’ouvre dans un nouvel onglet.
* Ajouter un bouton retour pour permettre aux gens de revenir facilement aux questions précédentes.
* Empêcher les lecteurs d’écran de lire les icônes décoratives.
* Veiller à ce que les messages d’erreur soient clairs et concis chaque fois qu’un utilisateur tente de naviguer sur une autre page sans sélectionner d’option.
* Changer la sélection de la province à partir de boutons radio à une conception hybride de remplissage automatique ou de liste déroulante suivant la conception de [remplissage automatique du gouvernement du Royaume-Uni](https://github.com/alphagov/accessible-autocomplete) (en anglais seulement).
* Restructurer les titres des prestations en code couleur et différencier les prestations offertes à l’utilisateur individuel, les autres aides et les prestations non disponibles pour cet utilisateur. La liste des prestations non disponibles a été réduite en accordéon. Cette structure facilite l’accessibilité des renseignements, tout en réduisant simultanément la charge cognitive.