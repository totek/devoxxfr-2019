## [De Java à un exécutable natif : GraalVM et Quarkus changent la donne](https://cfp.devoxx.fr/2019/talk/WUY-7299/De_Java_a_un_executable_natif_:_GraalVM_et_Quarkus_changent_la_donne)
**_Conference_**

### Thématique

Java, JVM, Javas SE/EE

### Hashtag

### Speaker

* [Emmanuel Bernard](https://www.twitter.com/@emmanuelbernard) - RedHat

### Slides

TODO

### Video

TODO

### Code

TODO

### Interest

5/5

### Summary

> Les microservices, la scalabilité instantanée et les plates-formes à haute densité comme Kubernetes nécessitent des applications à faible empreinte mémoire et démarrage rapide. Java n'était pas bien positionné car il favorise les temps de traitement aux dépens du CPU et de la RAM.
  
> Plus maintenant.
  
> Entre en scène Quarkus, une stack Java orientée microservices qui supporte vos composants favoris (Hibernate, Vert.x, Camel, RESTEasy ...) sur GraalVM et HotSpot avec une faible empreinte mémoire et un démarrage rapide. Tout ce qu'il faut pour tirer pleinement parti des containers.
  
> La gestion de la donnée est souvent l'aspect le plus complexe : découvrons comment Quarkus gère la persistance avec Hibernate ORM. Venez explorer le live reload, notre vision de la persistance avec Hibernate Panache, l'environnement de test, la compilation native GraalVM et bien plus. Quarkus se vit plus qu'il ne se verbalise, attendez-vous à une démo détaillée.

### Notes

#### Quarkus

Orienté cloud native, etc.

Live reload

Dépendances sont des extensinos pour Quarkus

Hibernate with Panache (entity extends PanacheEntity)

Quarkus fait de l'amélioration de bytecode : pas de plus value d'avoir des getters setters : donc attributs publics

Compilation lente (ahead of time), démarrage rapide.

**Problématique Java**

Pour une approche micro-service, occupation mémoire importante des petites applis Java

**Bénéfices**

- Optimized for dev
- zero config, live reload
- based on standards
- streamlined code to manage 80/20%
- conso mémoire
- startup
- unifies imperative & reactive code
- reuse frameworks already none

**GraalVM**

- libs java
- compiler
- substrate VM -> élimine le code mort, diminue meta space.
- Fourni native executable
- initialise tous les chemins à la compile pour le build et élimine ce qui n'est pas utilisé

**Caveats**

Closed world approach: no dynamic class loading

Se limite aux classes nécessaires, donc trade-off:
- Reflection (declaration manuelle dans une liste)
- dynamic proxy (declaration manuelle dans une liste)

#### comment ca marche

La problématique du startup time est reporté au build time.

Avantage: tout cela n'est fait qu'une fois, au build, d'ou le gain de temps au startup.

#### Extensions

Frameworks dependencies par extensions

Hibernate Panache: gain en code plus compact

Créer une extension: possible
Diff entre librairies et frameworks: soit faire une extension pour intégrer un framework, soit niveau graal vm 

### Feedback

Quarkus est une solution très performante pour "devops"er un vrai micro-service autonome respectant les principes 12 factor app.
- perfs en terme d'empreinte mémoire et runtime
- trade off à prendre en compte avant de se lancer

A essayer absoluement.

A découvrir:
- Hibernate Panache
