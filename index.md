
Table of content

- [Tools](#Tools)

## Libs

### Spring

#### Test

```
@SpringBootTest provides an application context and allow the usage of dependency injection
```

#### Web

```
@RestController @GetMapping @PostMapping
@PathVariable @RequestParam @RequestBody
```

#### Reactor

just : static creation
fromIterable
merge 

zip: take in order 
withLatestFrom

range(i, n) : integer flux
interval(n seconds) : emit event each n sec
take(n first)
skip(before n)
filter
map: 1 to 1 sync mapping
flatMap: 1 to N potentially async mapping


### Message Broker
#### RabbitMQ

Queue
Binding
Exchange
Routing-key
Message header

#### Kafka

Topic
Partition
Index
Registry

### JVM

#### java.util

```
joinToString(separator="")
Integer.toBinaryString(int i)
```


## Tools

### RabbitMQ

load testing : PerfTest

#### DLQ
* Not usefull for request/reply
* TTL/Queue capacity/Manual
* Set at the queue creation or dynamically via policy
* Binding on a dedicated dql exchange/routing-key

#### Exchange
fanout: broadcast ignoring routing key
topic: use routing-key, flexible configuration  

### Kubernetes (orchestrator)

kubectl get po --namespace <nmsp>

#### Helm (package manager)

client/server(Tiller)

###Api-Management 
 
#### Gravitee

### Git

```
git remote prune origin
git fetch -p && git branch -vv | awk '/: gone]/{print $1}' | xargs git branch -d
git reset HEAD~
```
 
### Maven

```
mvn install -U
mvn dependency:tree -Dverbose -Dincludes=[groupId]:[artifactId]:[type]:[version]
```

### Docker

```
docker run -p 9000:8080 --name myTomcatContainer tomcat 
```

### Base64

```
echo -n "blabla" | base64
echo -n "jhgtyk" | base64 -d
```

## Architecture

### Streams

Cold : won't start pumping until there's a subscriber et emit the whole dataset
Hot : live data, begins pumping on connection, consumer receive only newest data

### DDD

Very dumb and simplified definition : An approach where the domain remains at the center of everything

### CQRS

Command/Query segregation

### Event sourcing

One source of truth, multiple dedicated fast projections

Retry strategy

