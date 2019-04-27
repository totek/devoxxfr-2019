## [De Java 8 à Java 11 sur un gros projet : les pièges à éviter](https://cfp.devoxx.fr/2019/talk/GAI-1689/De_Java_8_a_Java_11_sur_un_gros_projet_:_les_pieges_a_eviter)
**_Conference_**

### Thématique

Java, JVM, Javas SE/EE

### Hashtag

### Speaker

* [Thomas Collignon](https://www.twitter.com/@collignont)
* [Alexis DMYTRYK](https://www.twitter.com/@AlexisD54)

### Slides

TODO

### Video

TODO

### Code

TODO

### Interest

3/5

### Summary

> Points d’attention importants pour une migration java 8 -> 11, et nous verrons en quoi cette migration peut être bénéfique pour vos projets.

> “Quel fournisseur de JDK choisir ?” C’est désormais un point à ne pas sous-estimer, surtout sur les projets longs termes.

### Notes

Suppression d'APIS
Dépendances problématiques
Outils

Java 8 : patch gratuits très probablement
Java 11: peut être pas

Migrer est bénéfique: nouvelles features, risque d'avoir trop de versions de retard.

Lien migration Java 11 sur le site d'orcale

Evol Java 9-11: très light

#### Distribution 

OpenJDK 11: Oracle? Adopt?

Manque de recul, attente de soir gestion des patches -> partir sur la distrib Oracle

#### Upgrade

Upgrade des outils Maven et plugins
compiler-plugin: 3.8.0
tools.jar: dep à supprimer

Attention aux plugins maven qui ne fonctionnent pas en JDK 11.

Au runtime, peux y avoir des problèmes et class not found. (outil de control bytecode)
Classes en doublon dans le code ou dependances transitives
Control Bytecode : dispo sur github

Jaxb supprimé du JDK

Libs de test:
Junit 4 ok
Assertj 3.11.1
Mockito 2
PowerMock: pas de support, fin de vie -> à banir

Reflections : attention. (voir ClassGraph)

Bien se cantoner aux standards pour éviter les surprises

Upgrade Sonar 7.4

Tomcat 9

#### Next steps

Se projeter pour Java 12-17

Penser à la modularité

Tester des compiles régulières des versions du JDK

Outils pour la modularité: plugin "deptective"
GraphViz

Ne pas migrer trop vite: attendre 3-6 mois surtout par rapport au suivi des outils utilisés (plugins, IDEs, serveurs...)


### Feedback

Bonnes pistes de reflection sur stratégie de migration à Java 11.

OracleOpenJDK : le bon choix apriori

Attention aux plugins et outils autour de votre écosystème et aux libs liées à la réflection.

Anticiper les prochaines versions intermédiaires de Java en faisant régulièrement des tests de compilation par exemple.
