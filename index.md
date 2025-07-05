
Table of content

- [Tools](#Tools)

## Libs

### Spring

**@Bean**

```
@Configuration
public class MyAppConfig {
  @Bean
  public DummyService dummyService(){
    return new DummyServiceImpl();
  }
}
```

**@Component**

specializations :

**@Service** : Heart of an app

**@Repository** : Handles data persistence

**@Controller** : Handles requests and reponses

Dependency injection : **@Autowired** Via a class field, a setter, the constructor (prefer for easy test)

#### Test

```
@SpringBootTest provides an application context and allow the usage of dependency injection
```

#### Web

* @RestController 
* @GetMapping 
* @PostMapping
* @PathVariable 
* @RequestParam 
* @RequestBody

#### Scopes

```
@Bean
@Scope("singleton")
```

Scope |	Description
----- |------------
singleton |	(default) A single bean instance
prototype |	A bean instance per usage
request |	A bean instance per HTTP request
session |	A bean instance per HTTP session
application |	A bean instance per Servlet Context
websocket |	A bean instance per WebSocket

#### Reactor

* just : static creation
* fromIterable
* merge 
* zip: merge two streams and take data in order 
* withLatestFrom
* range(i, n) : integer flux
* interval(n seconds) : emit event each n sec
* take(n first)
* skip(before n)
* filter
* map: 1 to 1 sync mapping
* flatMap: 1 to N potentially async mapping

### Processing engine
#### Flink
Stream based

#### Spark
Micro-batching based
Delayed result + artificial spiky load

### Message Broker
#### RabbitMQ

load testing : PerfTest for very very simple use cases


* Queue: a buffer that stores messages
* Binding: rules that exchanges use to route messages to queues
* Exchange: takes a message from producers and routes it into zero or more queues
* Routing-key: key used in routing :D

##### DLQ

* Not usefull for request/reply
* TTL/Queue capacity/Manual
* Set at the queue creation or dynamically via policy
* Binding on a dedicated dql exchange/routing-key

##### Exchange
* fanout: broadcast ignoring routing key
* topic: use routing-key, flexible configuration  

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

### Kotlin

* map: 1 to 1 
* flatMap: 1 to N
* Int.(String) -> Unit: function literals with receiver

#### Coroutines

* runBlocking: gateway between the suspendable and non-suspendable world
* Channel: acts like a pipe or a queue where one coroutine can send data and another can receive it



## Asynchronous Operations

### Backpressure
A mechanism where the consumer can signal to the producer how much data it can handle, preventing the consumer from being overwhelmed

### Handling a Stream of Multiple Values (0 to N items)
* Reactor: Flux
* Kotlin: Flow
* Java: Flow API (Java 9+)

### Handling a Single Value (0 to 1 item)
* Reactor: Mono
* Java: CompletableFuture
* Kotlin: Deferred

Concern	Java (Standard)	Project Reactor	Kotlin
Sync Stream (Multiple Items)	Stream	(Not applicable)	Sequence
Async Stream (Multiple Items)	java.util.concurrent.Flow	Flux	Flow
Async Single Value	CompletableFuture	Mono	Deferred
Coroutine Communication	(Not applicable)	(Not applicable)	Channel

## Tools

### Kubernetes (orchestrator)

kubectl get po --namespace nmsp

#### Helm (package manager)

client/server(Tiller)

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

* Cold : won't start pumping until there's a subscriber et emit the whole dataset
* Hot : live data, begins pumping on connection, consumer receive only newest data

### DDD

Very dumb and simplified definition : An approach where the domain remains at the center of everything

### CQRS

Command/Query segregation

### Event sourcing

One source of truth, multiple dedicated fast projections

Retry strategy

