

![Diagram](https://res.cloudinary.com/hevo/image/upload/f_auto,q_auto/v1642485693/hevo-learn/Kafka-Clusters-Kafka-Clusters-Architecture-Diagram.png?_i=AA)





**Topics** : set of messages that belongs to category of msgs. Unique identifier of a topic is its name

topics are split into partitions. Partitions are distributed into brokers

Msgs in partition are ordered and immutabile

**Replication factor** : copy/replica/backup of a paritition.

**Broker** : Kafka servers.

**Producer** : produce msgs.   They can produce msgs on topic level or partition level

**Consumer** : consume msgs.   They can consume msgs on topic level or partition level. Every consumer associated with some ***consumer group***

**Zoo Keeper** : Manage kafka cluster and cordinate with each broker

**Throughput** : Msgs read/write per second


**PubSub Model Explaination** : https://www.youtube.com/watch?v=FMhbR_kQeHw
