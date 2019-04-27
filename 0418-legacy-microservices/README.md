## [Synchronisation bi-directionnelle d'un legacy et d'une architecture micro-services](https://cfp.devoxx.fr/2019/talk/FIE-6391/Synchronisation_bi-directionnelle_d'un_legacy_et_d'une_architecture_micro-services)
**_Conference_**

### Thématique

Architecture, Performance et Securité

### Hashtag

### Speaker

* [Brice LEPORINI](https://www.twitter.com/@blep)

### Slides

TODO

### Video

TODO

### Code

TODO

### Interest

4/5

### Summary

> Si vous travaillez dans une startup, vous devez certainement monter votre architecture micro-services from scratch avec assez peu de dépendances. Toutefois dans bien des cas, votre architecture est prévue en remplacement d'un système monolithique existant. Evidemment toute migration de type big bang est proscrite et vous devez prévoir que les deux systèmes coexistent pour un longue durée et sont amenés à modifier des données de façon concurrente ... et en évitant tout conflit!

> Venez découvrir comment ce défi a été relevé pour un acteur de la grande distribution de premier plan.

### Notes

#### Contexte

Retail: migration progressive d'une appli de 15 ans vers archi micro-services

Event sourcing, CQRS, DDD, Data Streaming, Change data capture

#### Gradual migration

Strangler application pattern : Migrer les features au fur et à mesure + definition bounded context

On restreint sur une population de users (Canary releases) 

-> need concurrent modification by the legacy and new micro-service

#### How

On ne peut pas gérer les conflits.
Donc

Pendant canary release, le master de la data est le legacy. On réplique les changements dans les 2 systèmes.

**Synchro DB legacy avec le snapshot**

Using CDC: Change Data Capture
Logs changes of the DB, donc pas de change du système legacy
MSSQL: built-in, sinon Debezium

On gère des évènements technique et non métier.

Attention : ça crée une table compagnon de chaque table métier
Et pour chaque update d'une ligne métier, genère 2 lignes dans les tables CDC
-> tradeoff : pb de volumétrie, perfs.  Alternative: file systeme filling

Must deal with eventual consistency

#### Techno

Kafka: broker de messages, data streaming, immutable messages, ordered, distributed, scaling, etc...
-> no message can be lost

Il faut monitorer le lag qu'il y a entre les 2 systèmes pendant la perdiode Canary release.

Le datapath est circulaire

#### Rollout

Mise en prod d'un nouveau micro-service

Les modifs de data sont stockées dans Kafka, donc pas génant si la procédure de migration de data est longue.

Dès que la migration est proche de 0, on active le micro-service.

### Feedback

Architecture inspirante pour faire coexister un legacy avec migration graduelle vers des micro-services.

Le talk est assez riche en contenu, nécessite de bien creuser chaque sujet.

Repose sur CDC et events (et donc event sourcing, DDD, Kafka).

Attention à bien gérer les trade-off.
