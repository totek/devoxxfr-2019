## [JUnit : il serait temps de passer la 5ème !](https://cfp.devoxx.fr/2019/talk/TPC-2275/JUnit_:_il_serait_temps_de_passer_la_5eme_!)
**_Tools-in-Action_**

### Thématique

Agilité, Méthodologie & Tests

### Hashtag

### Speaker

* [Juliette de Rancourt](https://www.twitter.com/@ju_derancourt)
* [Julien Topçu](https://www.twitter.com/@JulienTopcu)

### Slides

https://slides.com/julientopcu/junit-il-serait-temps-de-passer-la-5me#/

### Video

TODO

### Code

https://gitlab.com/crafts-records/remember-me

### Interest

5/5

### Summary

> Saviez-vous que JUnit 5 a déjà plus d’un an ? Pourtant, un grand nombre de projets Java sont encore testés avec JUnit 4, qui est sorti… il y a 13 ans ! Enormément de choses ont évolué depuis 2006, Java a pris 6 versions ! Ne serait-il donc pas temps de remettre nos tests au goût du jour ?
  
> L’équipe JUnit a profité de cette 5ème version pour restructurer complètement le framework. De nombreuses features ont été ajoutées ou retravaillées afin de s’adapter aux nouveaux paradigmes de l’écosystème Java.
  
> Lors de ce talk, nous verrons que même si tout cela a introduit beaucoup de changements, les mécanismes de rétro et post compatibilité garantissent une migration facile et progressive.

### Notes

#### Migrer de 4 à 5
https://junit.org/junit5/docs/current/user-guide/#migrating-from-junit4
- junit:junit remplacé par junit-vintage-engine
- nouvelle version: junit-jupiter

#### Attention
- @Test a changé de package
- Renomage de la majorité des annotations

#### Nouveautés
Général:
- @Rule et exception deprecated: utiliser assertThrows
- assertAll() : permet d'y mettre plusieurs assert qui seront tous évalués et donner un rapport de test qui ne s'arrête pas au premier fail d'un assert
- @DisplayNameGenerator : se baser sur le nom des méthodes pour display propre dans le rapport
- Faire nos propres meta annotations

Tests paramétrés:
- @ParameterizedTest + @ValueSource + @NullSource
- @CsvSource si plusieurs paramètres
- @Methodsource

#### Extensions
Nouveau mécanisme d'extensions permettant notamment:
* Remplacer @RunWith(Spring...) par @ExtendWith(SpringExtension)
* Mettre plusieurs extensions sur la classe de test
* Créer nos propres extensions

Exemple d'extnesion que l'on peut créer: 
+ On met un objet en param de la méthode de test
+ Ce param est initialisé par un extension ParameterResolver - pratique pour les jeux de data

#### Divers
On peut tester les equals et hashcode avec des tests par interface.

Exemple: EqualityTest<T> : notre classe de test extends

Technique pratique par exemple pour tester différentes implem de la même interface.

### Feedback

Super demo de comment migrer vers Junit5 rapidement avec un couple de speaker qui fonctionne bien.

Examples exhaustifs et concrets.

Must see, must do: passer dès aujourd'hui à Junit 5.
