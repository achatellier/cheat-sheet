
Table of content

- [Tools](#Tools)

## Patterns

### DDD

### CQRS

### Event sourcing

### Visitor

### Facade

### Composition



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

### Kubernetes

kubectl get po --namespace <nmsp>

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


