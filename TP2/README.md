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
Au lieu de créer un objet on l'inject par le container

### Injection de ressource
```java
@Resource(lookup="java:app/mail/free")
private Session sessionEMail;
```
pour injecter un serveur d'email

### Injection avec CDI
```java
@Inject
A a;
```

### Portée du CDI
Durée de vie de l'objet (ex: une requête HTTP)
```java
@RequestScoped // HTTP
@ViewScoped
@SessionScoped
@ApplicationScoped
@FlowScoped // JSF pages
```

### Bean CDI dans JSF
```java
// BeanImprimante.java

@Named // Named("unNom")
@RequestScoped
public class Bean { } // Bean est le nom
```

```js
// page2.jsf

<h:inputText value="#{bean.nom}"/>
```

## Contexte des EJB

### Interface javax.ejb.EJBContext
Interface d'un EJB avec contexte extérieur
- Interface fille SessionContext

```java
@Resource
private SessionContext context;

public void m(...) {
    if (...) context.setRollbackOnly();
}
```

## Transactions dans les EJB

### 2 types
- par le container (*CMT: Container Managed Transaction*)
- par l'EJB (*BMT: Bean Managed Transaction*)

### CMT
Container **démarre** et **termine** les transactions
```java
@TransactionAttribute(REQUIRES_NEW)
```
#### Attributs
- NEVER
- NOT_SUPPORTED
- SUPPORTS
- REQUIRED
- REQUIRES_NEW
- MANDATORY

### BMT
Plus de liberté dans la gestion des transactions
```java
tx.begin();
tx.commit();
tx.rollback();
```

## Exceptions dans les EJB
2 types
- `RemoteException` (erreur réseau)
- `EJBException` (erreur EJB)

### Traitement exception système
Container attrape l'exception et : 
- marque la transaction pour un rollback
- log
- enveloppe l'exception

## Service de timers
Lance méthode EJB à intervalles réguliers

### Types
- Automatique 
```java
@Schedule
```
- Crée par programmation
```java
@Timeout
```