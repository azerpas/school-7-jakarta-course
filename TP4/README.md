# CM4

# JPA (Jakarta Persistance API)
- ORM (vision objet)
- Couplé avec JDBC

## Entité
```java
@Entity
public class Departement {
    @Id
    @GeneratedValue
    private Long id;
    
    @OneToMany(mappedBy="dept")
    private List<Employe> employes = new ArrayList<>();
}
```

### Clé composite
Clé primaire de plusieurs colonnes
```java
@EmbeddedId 
@IdClass
```

### Configuration
- `META-INF/persistence.xml`
#### Définition d'une source de données

```java
@DataSourceDefinition(
    name = "java:app/jdbc/b1",
    className = "com.mysql.cj.jdbc.MysqlDataSource",
    portNumber = 3306,
    ...
)
@Stateless
public class MonEJBConnector() { 
    @PersistenceContext(unitName = "employes")
    private EntityManager em;
}
```

## Types
### Basic
- int, double
- String, BigInteger, BigDecimal, byte, char
- Time, Date, Calendar
- Enum 
### Embeddable
```java
@Embedddable
public class Adresse {
    private int numero;
    private String rue;
}

@Entity
public class Employe {
    @Embedded // All fields get copied from Adresse class
    private Adresse adresse;
}
```

## Entity Manager
### Géré par l'app
- On crée des EM avec une EntityManagerFactory
```java
private EntityManager em = emf.createEntityManager();
```
### Géré par le container
- Injecté directement par le contaier
```java
public class DeptFacade() { 
    @PersistenceContext()
    private EntityManager em;
}
```

### Méthodes
- `void persist(Object entité)`
- `<T> T merge(T entité)`
- `void remove(Object entité)`
- `<T> T find(Class<T> classeEntité, Object cléPrimaire)`
- `void flush()`
- `void lock(Object entité, LockModeType lockMode)`
- `void refresh(Object entité)`
- `void close()`
- `void clear()`
- `void detach(Object entity)`
- `Query createQuery(String requête)`
- `Query createNamedQuery(String nom)`
- `Query createNativeQuery(String requête)`