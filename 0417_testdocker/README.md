## [Tests fonctionnels avec Docker et TestContainers](https://cfp.devoxx.fr/2019/talk/MJU-5843/_Tests_fonctionnels_avec_Docker_et_TestContainers)
**_Tools-in-Action_**

### Thématique

Cloud, Containers et Infrastructure, DevOps

### Hashtag

### Speaker

* [Vincent Massol](https://www.twitter.com/@vmassol)

### Slides

TODO

### Video

TODO

### Code

TODO

### Interest

4/5

### Summary

> En tant que développeur, qu'il est bon d'être capable de débugguer sur sa machine un problème survenant en production, dans une configuration spécifique ! C'est ce que permet le framework TestContainers. Il permet de piloter Docker directement depuis ses tests JUnit et donc d'avoir un mécanisme extrêmement efficace pour déployer ses tests fonctionnels dans un environnement donné.

> Cette session présentera TestContainers, appliqué à un cas réel avec une démonstration de comment l'utiliser pour effectuer des tests impliquant une base de données, un moteur de Servlet et plus. Au programme: Intégration JUnit5, création d'images Docker custom, enregistrement automatique de vidéos des tests, intégration avec un job Jenkins pipeline pour itérer sur les différentes configurations à tester.

### Notes

Configuration Testing with Docker.

Context: XWiki that runs on different configurations (DBs, servers, etc.)

1 docker par configuration

**TestContainers**

Solution to test docker configuration. 
- Good to reproduce and debug locally in the IDE without dependencies on CI
- JUnit 5 to extend it
- Records videos

Features:
- built-in containers
- records videos
- auto cleanup
- full docker api
- create docker images on the fly

Advantages:
- easy to reproduce prod bugs
- configuration testing in IDE and debugging
- consistent behavior

Autres pistes ?
- Arquilian...

### Feedback

Must pour faire des tests de configurations si votre application est sous Docker et doit être déployée dans différents contextes (DB, JDKs, servlet containers...).

S'intègre dans le pipeline CI/CD.
