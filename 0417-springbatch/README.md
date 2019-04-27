## [Pimp up your Spring Batch en streaming avec Spring Cloud Data Flow et Kafka !](https://cfp.devoxx.fr/2019/talk/YCD-9021/Pimp_up_your_Spring_Batch_en_streaming_avec_Spring_Cloud_Data_Flow_et_Kafka_!_)
**_Tools-in-Action_**

### Thématique

Architecture, Performance et Securité

### Hashtag

### Speaker

* [Adriana Nitescu](https://www.twitter.com/@JPeachseed)

### Slides

TODO

### Video

TODO

### Code

- https://github.com/adreeana/demo-scdf

### Interest

5/5

### Summary

> Votre organisation a probablement des applications batch développées comme des monolithes, et en 2019 ça commence à faire désordre ! Comment faire pour les rendre plus exploitables, scalables et déployables dans le cloud, et soyons fous, comment les convertir en streaming ?
  
> C'est possible et nous montrerons la démarche avec du code, des diagrammes et des démos sur une migration d’un ETL vers une application de type pipeline de données avec Spring Cloud Data Flow et Kafka. Ou comment mettre du SWAG dans vos vieux batchs !

### Notes

**Contexte**

Applis qui intégrent et échangent des giga de données.

Spring batch:  Jobs > steps

Si nécessite bcp de serveurs de traitement, une config manuelle devient ingérable
-> on veut scaler, rendre réutilisable

**Solution**

On split en plusieurs petites appli connectées à un broker.

On veut scaler automatiquement : Spring Cloud Task (tasks à durée de vie limitée) + Spring Batch => on déploie dans le cloud

Pour durée de vie illimitée:  Spring Cloud Stream + Kafka

Comment: une annotation @EnableBinding + des plugins maven

Avec approche DDD permet de découpler.

**Infrastructure**

Spring Cloud Data Flow (existe pour Kubernetes)

Tous les jobs de batch deviennent des tâches (@EnableTask, @EnableBatchProcessing)

Configuration des stream et task dans la console d'admin Spring Data Flow

Monitoring avec Grafana

**Pourquoi**

* Facile de migrer des Spring batch dans le Cloud (même si on ne split pas).
* Domain indépendant de l'infra
* Indépendant du middleware (Kafka ou autre)
* Communauté Spring
* Cloud foundry, Kubernetes dispos
* On se concentre sur l'appli et moins sur l'infra

### Feedback

Exemple très simple et parlant pour comprendre l'architecture à mettre en place dans ce contexte de scalabilité avec Spring Batch.
Va à l'essentiel.

A garder:
- Songer à intégrer la stack Spring Cloud.
- Puissance de la scalabilité pour du batch processing
