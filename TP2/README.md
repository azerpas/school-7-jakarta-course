[← Home](../README.md)    
[→ TP2](https://github.com/azerpas/school-7-jakarta)

# CM2

# EJB
Composant annoté pour objets métiers et BDD

## Gestion
- Cycle de vie
- Sécurité
- Threads
- Concurrence
- Transactions

## Avantages
- Dév focus traitements "métiers"
- Dév pas à gérer sécurité, concurrence, etc...

## Intégration avec JSF
JSF communique avec les *backing beans* -> qui font appel aux EJB

**Bientôt: EJB remplacé par beans CDI**

## Interfaces
EJB s'expose à classes, mais c'est un "proxy" du container qui reçoit les messages et les délègue à l'EJB

### Exemple

#### Interface
```java
@Remote
public interface Hello {
    public String ditHello(String nom);
}
```

#### EJB - Implémentation
```java
@Stateless
public class HelloBean implements Hello {
    public String ditHello(String nom){
        return "Hello,| " + nom;
    }
}
```

#### Client de l'EJB
```java
public class Clinet {
    @EJB
    private Hello ejbHello;

    public void m(){
        String s = ejbHello.ditHello(unNom);
    }
}
```

## Types
### EJB Session
- sans/avec état
- singleton

### EJB Message-Driven Bean

## EJB Session
- public, pas final / abstract
- constructeur sans paramètre
- args et retour des méthodes "remote" doivent être de type *RMI*

### Exemple
```java
@Stateless
public class EJB1 {
    @EJB
    private EJB2 autreEJB;

    @PostConstruct
    public void init() {
        // Initialisation qui utilise autreEJB
        // ...
    }
}
```

### Supression
Libère ressources de l'EJB
```java
@PreDestroy
```

### Sans état
- Exécute une tâche, une méthode
- Intéraction:
    - appel méthode
    - fin de méthode
- Aucune info entre 2 appels de méthode
- Notion de pool

### Avec état
- Exécute une tâche, plusieurs méthodes
- Info entre 2 appels de méthode
- Conversion client - serveur
#### Suppression 
```java
@Remove
```

## EJB singleton
```java
@Singleton
// @Startup: instance créée au déploiement
```
- Instancié une seule fois par un container EJB

## Appel asynchrone d'une méthode
Interdit à un EJB de créer des threads mais:
```java
@Asynchronous
```
permet d'exécuter la méthode en parallèle dans un thread

## Injection de dépendance