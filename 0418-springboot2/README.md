## [Applications web efficaces avec Spring Boot 2](https://cfp.devoxx.fr/2019/talk/SHR-7581/Applications_web_efficaces_avec_Spring_Boot_2)
**_Conference_**

### Thématique

Java, JVM, Javas SE/EE
 
### Hashtag

### Speaker

* [Stéphane Nicoll](https://www.twitter.com/@snicoll)
* [Brian Clozel](https://www.twitter.com/@bclozel)

### Slides

N/A

### Video

TODO

### Code

https://github.com/snicoll-demos/initializr-stats

### Interest

4/5

### Summary

> Comment peut-on améliorer l'efficacité et la scalabilité d'une application web existante? On pourrait complètement la réécrire, avec programmation plus concurrente, fonctionnelle, ou réactive. Mais est-ce que ça vaut vraiment le coup, sans mesurer et savoir où concentrer nos efforts?
  
> Dans cette présentation, Stéphane et Brian vont travailler sur une application Spring Boot MVC existante pour la rendre plus efficace. Ils vont remplacer RestTemplate par WebClient et utiliser des opérateurs Reactor pour améliorer la scalabilité, sans tomber dans les pièges de la programmation concurrente.
  
> Ils vont utiliser des métriques fournies par Spring Boot, en ajouter des personnalisées, et garder un oeil sur les gains de capacité dans des dashboards.

### Notes

Spring Boot 2: donne le choix entre la stack reactive ou servlet.

Dependance à ajouter dans son projet: spring-boot-starter-webflux

**WebClient**

Remplacer RestTemplate (qui va être déprécié) en faveur de **WebClient**.

Utiliser WebClient.Builder.

Permet de conserver le stack servlet classique tout en étant prêt à migrer vers reactif.

Plugin navigateur de live reload avec devtools.


### Feedback

WebClient vs RestTemplate (deprecated soon)
-> A migrer tout de suite même en restant en mode non reactif: prêt pour évoluer.

Penser à devtools.
