# TP Symfony: Gestion des formations

- [TP Symfony: Gestion des formations](#tp-symfony-gestion-des-formations)
  - [Utilisateur cible](#utilisateur-cible)
  - [Persistence des données](#persistence-des-données)
  - [Entitées](#entitées)
  - [ERD simple](#erd-simple)
  - [ERD détaillé](#erd-détaillé)

Le but de ce TP est de créer un site web qui permet de gérer les formations.

Plusieurs entitées sont à prendre en compte dans ce site (cf: [entitées](#entitées)).

L'idée est de facilité la gestion des formations et leurs ressources.
Un utilisateur de ce site devrais pour gérer:

- les *candidat*s
- les *formation*s
- les *formateur*s
- les *salle*s dans lesquelles se déroulent les *formation*s
- les *session*s auxquelles les *candidat*s participent (sujet de formation exemple: "Angular", "Symfony", "Agile et Scrum", etc.)
- les *organisme*s de formations qui vendent leurs *formation*s
- les *promotion*s (groupes de *candidat*s) avec leur(s) *formateur*(s) référent(s)

## Utilisateur cible

Ce site est déstiné aux partenaire pédagogiques qui répondes aux demande des organismes de formation pour placer des formateurs sur différentes sessions.

Il faut donc un site avec une interface utilisateur.

## Persistence des données

Symfony s'occupera de la partie présentation et métier de l'application. Pour la persistance il est préférable d'utiliser une base de données relationnelle (par exemple: MySQL, MariaDB ou Postgresql).

> Vous pouvez accélérer la mise en place de la base de données avec [Docker](https://www.docker.com/)

## Entitées

- formation
  - intitulé
  - organisme de formation
- organisme de formation
  - nom
  - adresse
  - numero de telephone
  - email de contact
- formateur
  - nom
  - prenom
  - numero de telephone
  - email
- promotion
  - nom
  - formation
  - referent (formateur)
- session
  - date_debut
  - date_fin
  - nom (de la session)
  - formateur
  - promotion
  - salle
- candidats
  - nom
  - prenom
  - adresse email
  - numero de téléphone
  - promotion
- salle
  - nom
  - session

## ERD simple

Il est conseillé de partir sur ce type de relation entre vos entitées (vous pouvez compléter librement les attributs de ces entitées)

[![ERD simple](https://mermaid.ink/img/pako:eNpd0cFuwyAMBuBXiXxu-gC5bt11k3LlYoGbWQs4MuRQJXn3AUkrNVz5_P8WLGDFEXRA-sk4KHoTvkQ9JpbQbGvbrmvzrQMGjp66xsCkMkkkAyb8qHipcJXrNcPXZIEcolVOJ7gn7pBmLZCCRac1sacYa3HOk-XMIvEQ3t0e98qvC6ImtjxV-IHBscO0Fy_v8o6cmsrrlj2OI-Xqts3VR0NhaO1MnO8KMqE5HbiAp7wnu_yMS7k3kH7JZ16mHepfGdyym6e8Ct0cJ1Ho7jhGugDOSfpHsNAlnemJjt841PYPmqKT7g)](https://mermaid.live/edit#pako:eNpd0cFuwyAMBuBXiXxu-gC5bt11k3LlYoGbWQs4MuRQJXn3AUkrNVz5_P8WLGDFEXRA-sk4KHoTvkQ9JpbQbGvbrmvzrQMGjp66xsCkMkkkAyb8qHipcJXrNcPXZIEcolVOJ7gn7pBmLZCCRac1sacYa3HOk-XMIvEQ3t0e98qvC6ImtjxV-IHBscO0Fy_v8o6cmsrrlj2OI-Xqts3VR0NhaO1MnO8KMqE5HbiAp7wnu_yMS7k3kH7JZ16mHepfGdyym6e8Ct0cJ1Ho7jhGugDOSfpHsNAlnemJjt841PYPmqKT7g)

## ERD détaillé

Si vous manquez d'inspiration pour les champs vous pouvez vous inspirer ce ce diagramme à la place

[![ERD plus complet pour le projet formation](https://www.planttext.com/api/plantuml/svg/hLJRQkCm47tNLmnvAIou7n1AAHJQXttemdv0KAI9CrGN8yaj9V6_xzY9vKjZiopxvXcTEUVCZEIdc6H8jJL2tC6HD48w8iJA9z55Ye8os1xA3qyQgk3t1cs4Jqf7aAuqg445_ndXW9X4V2TNoI0j67AOlYe47zBH2v4e6OHNZ8cy0urSu8ELRHI54EWOy0KlVGvE0k37WDcHteAhxHu3F3oKw338XFhnaM55qM6ffQWDRY6cGAxiaZwKqb6qE2Lu-ScLJPPzwr5NsOMgcxBEsucYr05ZdBfW1Wn-bz1CqcWbcPtoBacLyaapcmRMOJ8DZl_1LXLmdbfpTSFDh-2j7-scwkFEJIPOq5_OPBU8bTvcY_hDenqSn4iqgkZr0JIJxJJkQnvi-pqa3-HoQiddRHzBNO_FepHc_R8zIwU9zQzDg6luVtPw-qgjR7kjdoQFlMsg7_ht1l_Ax7XPSnanlFlcN1Jdy_0Yjx1XYvMFk1733Jpx-tj6vJ96aOigK9gWBbpv6J4AdMeVw4RqDwbX9d-QOI9IwSQW2r5cRatnVvCKLOpA2-tqJXFOGLA23ilEBcDiV56mufMRCLAf6ecFDa8yeTFyE_u3)](https://www.planttext.com/?text=hLJRQkCm47tNLmnvAIou7n1AAHJQXttemdv0KAI9CrGN8yaj9V6_xzY9vKjZiopxvXcTEUVCZEIdc6H8jJL2tC6HD48w8iJA9z55Ye8os1xA3qyQgk3t1cs4Jqf7aAuqg445_ndXW9X4V2TNoI0j67AOlYe47zBH2v4e6OHNZ8cy0urSu8ELRHI54EWOy0KlVGvE0k37WDcHteAhxHu3F3oKw338XFhnaM55qM6ffQWDRY6cGAxiaZwKqb6qE2Lu-ScLJPPzwr5NsOMgcxBEsucYr05ZdBfW1Wn-bz1CqcWbcPtoBacLyaapcmRMOJ8DZl_1LXLmdbfpTSFDh-2j7-scwkFEJIPOq5_OPBU8bTvcY_hDenqSn4iqgkZr0JIJxJJkQnvi-pqa3-HoQiddRHzBNO_FepHc_R8zIwU9zQzDg6luVtPw-qgjR7kjdoQFlMsg7_ht1l_Ax7XPSnanlFlcN1Jdy_0Yjx1XYvMFk1733Jpx-tj6vJ96aOigK9gWBbpv6J4AdMeVw4RqDwbX9d-QOI9IwSQW2r5cRatnVvCKLOpA2-tqJXFOGLA23ilEBcDiV56mufMRCLAf6ecFDa8yeTFyE_u3)
