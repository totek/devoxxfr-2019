## [Title](link)
**_Format_**

### Thématique

### Hashtag

### Speaker

* [Florent Ramière](https://twitter.com/framiere)
* [Jean Louis Boudart](https://twitter.com/jlboudart)

### Slides

### Video

### Code

### Interest

### Summary
> quote

### Notes

#### Penser à la durabilité

Fonctionement: Store dans la cache et flush dans le disque après

**faire de la réplication**

**de la conf**

acks=all for durability -> reçoit le ack une fois que tous les replicas sont synchro)
Faire du min.isr=2 au moins

**Multi datacenters**

Consulter la doc pour le DR

**Consumers**

Watermark posé dès que la data est répliquée

whitepaper: Optimzing your Apacha Kafka deployement


#### Gestion d'erreurs

**Retries** (0 par défaut - infini dans la version 2)
Utiliser le mécanisme dispo

**Message duplication**
enable.idempotence au niveau du producer (false par défaut: mettre à true - un UUID est utilisé)

**Config des consumers**
at least once (par default)

commit -> risqué placé au mauvais endroit ou mauvais moment

-> embrace at least once (use Kafka Streams)


### Feedback

Must read avant de penser à la Prod.
Aussi pendant le design par rapport aux tradefoff à considérer.

