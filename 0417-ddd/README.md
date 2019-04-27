## [Applying (D)DDD and CQ(R)S to Cloud Architectures with Java, Spring Boot, Kafka and Docker](https://cfp.devoxx.fr/2019/talk/DTB-8240/Applying_(D)DDD_and_CQ(R)S_to_Cloud_Architectures_with_Java,_Spring_Boot,_Kafka_and_Docker)
**_University_**

### Thématique

Architecture, Performance et Securité

### Hashtag

### Speaker

* [Benjamin Nothdurft](https://www.twitter.com/@dataduke)
* [Michael Follmann]()
* [Dominik Guhr]()

### Slides

- http://slides.com/dataduke/2019-04-17-ddd-cqrs#/
- http://slides.com/dataduke/2019-02-19-event-storming-180#/
- Blog: https://www.codecentric.de

### Video

TODO

### Code

N/A

### Interest

5/5

### Summary

> Many software architectures may benefit from the introduction of (Distributed) Domain-Driven Design and Command Query (Responsibility) Separation. No matter if you are maintaining large legacy software systems whether you start a new microservices platform as greenfield approach one always has to think about the domain language and service design. In this session I want to show you at a given example application how to get started with introducing domain models, bounded contexts and implementing CQRS where it makes most sense while trying to avoid the technical debt trap e.g. misconceptions and fallacies.

> The session consists of several parts which outline the theory behind the building blocks in conjunction with according real world implementation examples. The provided code is based on modern technology standards: Java, Kotlin, Spring (Boot, REST, JPA, Messaging), RabbitMQ, Kafka, MySQL, Elasticsearch, Docker, Kubernetes.

### Notes

Context: e-commerce
Books: DDD + implementing DDD

#### DDD : 2 parts
* Tactical design (Service - architecture)
* Strategic design (domain - building blocks)

#### Event storming

_Lightweight method to develop a domain - iterate layer by layer in workshops_

* Domain events : pin orange notes in a timeline board by all the domain experts
* Command-Event pairs : pin blue notes next to orange ones (triggers a domain event)
* Aggregates (~Entities) : link blue and orange notes -> facilitates to think about vocabulary -> glossary
* Borders & flows : draw borders where a domain nodel has a different meaning + arrows to show domain events flow between models
* Bounded context (sub-domain) : red sticky note with core name that is relevant
-> outcome : having a big picture - multiple story telling and common language

* Iterate / color puzzle thinking : add new colours to reveal pain points. Cross perspective conversation

* Bounded contexts > microservices
* Sub-domain : implemented as vertical

#### Terms

* Ubiquitous language
* Bounded context
* Domain model
* Context map (relation between bounded contexts)

#### System architecture

Context map patterns: 

**upstream**
- Open host service (REST, SOAP)
- Event publisher (messaging, feeds)

**in-between**
- Shared Kernel (shared subset of domain model - shared in a lib or DB)
- Published language (a model that we publish to external systems)
- Separate ways (no connection between them : can find their own solution)

**downstream**
- Customer / supplier (can have veto rights, negociate contract)
- Conformist (no veto rights, conforms to the same model)
- Anti corruption layer (translates external to internal model)

#### CQRS

Command Query Responsibility Separation
-> Separate command model from query model (posting and gettings have different concerns or needs)
2 solutions examples.
 
**With 2 microservices**

Event bus between 2 storages (broker).
Asynchrone, scalable.

Outline of DDD building blocks
* Model driven design : service building entities/ vo / aggregates an store them in repositories
* Publisher : publish the events
* DomainMessage
* Broker to handle messages for events and commands
* Subscriber
* Entity : no framework, keep it pure Java (use MapStruct for mapping to repo objects)

#### Cloud architecture

CI/CD pipeline

With CQRS, needs more complexity in the pipeline: docker image for RabbitMQ that needs to be done on build stage, acceptance stage, etc.


### Feedback

Overview des concepts d'architecture inéhrents à la mise en ouevre du DDD.

Le dernière partie sur le cloud / CI/CD un peu floue manque d'intérêt.

Examples de code à regarder de prêt.

A creuser:
- les solutions CQRS sont plus nombreuses que celles exposées.
- event sotre architecture
