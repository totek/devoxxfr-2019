## [Hexagonal at Scale, où l'art de découper et organiser ses services](https://cfp.devoxx.fr/2019/talk/GDA-0693/Hexagonal_at_Scale,_ou_l'art_de_decouper_et_organiser_ses_services)
**_Conference_**

### Thématique

Architecture, Performance et Securité

### Hashtag

### Speaker

* [Cyrille Martraire](https://www.twitter.com/@cyriux)

### Slides

TODO

### Video

TODO

### Code

### Interest

5/5

### Summary

> Les Microservices ont absolument besoin de DDD. La notion de Bounded Contexts, un ingrédient-clé de DDD, est l'outil de choix pour définir des contours de services qui ne vont pas mener au désastre au runtime et ou au moment de déployer. Ce talk vous donnera une meilleure compréhension de ce concept et de son intérêt dans le contexte d'une architecture de plus en plus distribuée. Surtout, vous découvrirez comment vraiment découper votre monolithe avec de nombreux conseils. Nous évoquerons aussi quand appliquer, ou non, le style Hexagonal, parce qu'il ne faut pas abuser des bonnes choses. Et tout cela avec du fun et quelques surprises !

### Notes

Partitioning
-> Bounded Context

Ce qu'il faut faire:
- Split by functional area = Use the Single Responsibility Principle
- Raisoner "métier"
- Testing boundaries

Principe DDD : Strategic design 

Nomage des sub-domains: "-ing", "-tion"

En général, les thématiques suivantes sont des bounded contexts:
- Search
- Reporting

Travailler par similitude avec d'autres métiers pour aider à découvrir ses sub-domains.
Différentes organisations, different shapes...

Même si il peut y avoir des similitudes entre les sub-domain, on peut implémenter différemment dans chaque bounded context.

Architecture hexagonale: Alistair Cockburn (http://wiki.c2.com/?HexagonalArchitecture/)

Selon le contexte, faire de l'hexagonal light: pas obligé de forcément tout appliquer, rester pragmatique.

Selon les bounded context:
- faire de l'hexa ou pas
- utiliser un progiciel
- technos différentes
=> faire de la fractal architecture

Bouquin: Living Documentation

### Feedback

Fournit de bonnes pistes pour bien cerner comment implémenter du DDD.

Selon le context, rester pragmatique et ne pas forcément essayer de faire DDD ou hexa de partout.
