
Table of content

- [Tools](#Tools)

## Libs

### Spring

```
@SpringBootTest provides an application context and allow the usage of dependency injection
```

```
@RestController @GetMapping @PostMapping
@PathVariable @RequestParam @RequestBody
```

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

### Gravitee

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

### DDD

An approach where the domain remains at the center of everything

### CQRS

Command/Query segregation

### Event sourcing

One source of truth, multiple dedicated fast projections

Retry strategy

