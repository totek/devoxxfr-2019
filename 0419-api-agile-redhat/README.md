## [Une API, de l'idée à la production, en mode agile avec Red Hat !](https://cfp.devoxx.fr/2019/talk/OWQ-3436/Une_API,_de_l'idee_a_la_production,_en_mode_agile_avec_Red_Hat_!)
**_Conference_**

### Thématique

Agilité, Méthodologie & Tests

### Hashtag

### Speaker

* [Nicolas MASSE](https://www.twitter.com/@nmasse_itix)
* [Laurent Broudoux](https://www.twitter.com/@lbroudoux)

### Slides

TODO

### Video

TODO

### Code

TODO

### Interest

4/5

### Summary

> C’est un fait, toutes les sociétés se muent en éditeur de logiciel et le développement d’API en mode agile devient une obligation pour rester pertinent et survivre. Cependant, cela peut être rendu difficile car les nouvelles architectures micro-service font exploser le nombre de dépendances ! Il est donc temps d’envisager un nouveau moyen de fournir des API (mocking et tests inclus) pour simplifier et accélérer le processus de livraison des API, de l’idée à la production.

> Dans cette session, nous allons passer en revue l’approche de Red Hat pour le développement d’API. Vous apprendrez comment:
> - utiliser le mocking pour aller plus vite et éliminer les dépendances
> - utiliser une approche “contract-first” pour définir des tests qui fiabiliseront votre implémentation
> - protéger l'API exposée via une API Gateway
> - et enfin sécuriser les livraisons à l'aide d’un pipeline CI/CD.

> 100% démonstration, la session se veut divertissante au travers d’un petit jeu de rôles. Nicolas sera le chef de projet, impatient de voir son API arriver en production et Laurent sera l’architecte qui lui viendra en aide lors des innombrables péripéties.

### Notes

Focus: cycle de vie d'une API

#Ansible (automatisation)

**Start**
Pas bcp de spec...
-> faire une sandbox : microcks.apps on peut générer une API . permet de mocker

**Next: un MVP**
Outil: Apicurio -> design de l'API
On défini ses entités et la liste des paths de son API
-> on fait un schéma qu'on peut exposer.

**Mettre à dispo un Mock pour les consomateurs**
Microcks + Postman
On peut donner des exemples pour utiliser notre API. Peut servir de doc.
Après on peut exporter et mettre dans GIT
On peut ensuite importer dans Microcks depuis le repo GIT -> le mock es prêt et versionné

**Phase de Dev/CD**
On veut deployer une version
-> Cluster openshift -> distrib Kubenetes de Redhat

**Tests**
Sur Postman on peut ajouter des requirements
-> va se retrouver dans fichier d'export
-> microcks on lance les tests Postman sur le endpoint

**Mise en prod**
OpenShift
-> on peut y faire differents envs
-> promouvoir l'appli d'un env à l'autre
-> création Pipeline  CI/CD
Réutilisation des Tests dans la pipeline pour les tests de non régression

**Secu/gouvernance**
Solution d'API management
Une micro gateway avec Three scale management.
On peut apporter des configs: secu, right control, etc
Analytics dispo

**Outage**
Politiques d'utilisation à définir dans l'API management
Mettre des limites, pricing, etc.

SOAP UI possible avec microcks
On peut faire des smoke tests dans microcks (défini manuellement dans le pipeline Jenkins)

On peut utiliser des plugins pour intégrer avec des éléments externes

APIcurio:
on peut y importer des swagger
On peut aussi collaborer dessus
La publication est manuelle: on publie dans le repo les modifs que l'on veut

Microcks:
Une seule instance par organisation (pas mutli orga...)

Tout est en OpenAPI. On attend 3scale

### Feedback

Démo d'outils (tous open source) pour crafter ses APIs:
- Microcks - mocks et tests (microcks.github.io)
- APICURIO - API spec (apicur.io)
- Postman - examples et tests
- OpenShift - CI/CD cluster
- 3Scale - api management
- SpringBoot
- Jenkins

RedHat Use: à checker
