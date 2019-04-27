## [PostgreSQL c'est le nouveau NoSQL](https://cfp.devoxx.fr/2019/talk/DRV-0739/PostgreSQL_c'est_le_nouveau_NoSQL)
**_Conference_**

### Thématique

Big Data, Machine Learning, Analytics
 
### Hashtag

### Speaker

* [Laurent Doguin](https://www.twitter.com/@ldoguin) - Clevercloud

### Slides

TODO

### Video

TODO

### Code

TODO

### Interest

5/5

### Summary

> Est ce que vous avez vu les dernières nouveautés des RDBMS traditionels? C'est assez dingue. Ils rattrapent les bases NoSQL à vitesse grand V. On avait déjà le support de JSON côté RDB?S et SQL côtés NoSQL, Mais ça va beaucoup plus loin maintenant.
  
> Les dernières version de PostgreSQL ajoutent de nouvelles fonctionnalités comme le table partitioning, query parallelism, un framework pub/sub, un nouveau système de quorum pour la synchro de données. On peut ajouter une amélioration des fonctions de fenêtre glissante pour facilité la requêtabilité des séries temporelles. On voit aussi apparaître de nouveaux drivers réactifs et asynchrones qui était plutôt l'appanage des DBs NoSQL jusque là.
  
> Et il se trouve qu'on utilise certaines de ses nouvelles fonctionalités chez Clever Cloud. Dans ce talk je vous montrerai certains d'entre elles pour essayer de vous convaincre que oui, PostgreSQL c'est le nouveau NoSQL.

### Notes

#### Contexte

DBs -> many... very rich choice

Now: hyperconvergence -> vers du multimodel

(PostgreSQL est une base ACID)

#### NoSQL

Rappel du CAP theorem (Consistency Availability Partitioning)
-> choisir le tradeoff

NoSQL = all that is not an RDBMS

Reasons to switch
- we hate SQL syntax
- on fait du ORM -> mais on y revient
- RDBMS Lack of: schemaless, scalability, failure ready (cloud native), multimodel (on veut faire tout, du graph, du relationnel ,etc.), platformization

#### PostegreSQL

Croissance fulgurante (DB la plus aimée sur stackoverflow)

**Pourquoi est-ce noSQL**
- schemaless (flexible on peut y mettre ce qu'on veut)
- support du json et jsonb data

**Avantages par rapport aux autres bases noSQL**
- support requetage json (tradeoff: un peu d'overhead)
- permet d'indexer le json

**Scaling**

Base ACID vs CAP theorem

Sharding (partage de la data) et replication (master/slave)

Replication logique (rejouer les écritures)

Avant, le sharding devait être fait à la main (vs ce que proposent les autres noSQL).

Réplication logique fonctionne sur un mode publish/subscribe simple.

Table sharding: distribuer une table sur plusieurs machines

**Performances**

Extensions pour faire des queries parallèles

Machine learning comming

Scaling -> loi de murphy

**Demo**

- 2 nouveaux drivers pour PostgreSQL
- Conseillé: R2DBC (driver reactif vs jdbc : fournit des options pour faire qq chose lors de failures)
-> fonction retryBackoff

#### NewSQL?

1 DB qui fait tout vs many DB pour splitter

#### More

Ajout de fonctions pour faire de la time series

#### Conclu

Marche pour 90% des use cases -> la base multimodel qui s'opère bien

### Feedback

Explique les bonnes raisons pour lesquelles c'est le choix pour résoudre 90% des use cases RDBMS et noSQL.

Adapté pour faire du relationel ET features du noSQL avec scaling, cloud native ready, reactive drivers.
