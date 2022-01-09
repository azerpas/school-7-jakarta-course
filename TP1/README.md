[← Home](../README.md)

# CM1

# Serveur d'application
Logiciel structure d'accueil, ex:
- GlassFish
- Payara

## Composants
Pour EJB, JSF: 
- réutilisable
- configurable
- interfacable

### Intérêts
- Maintenance
- Dév rapide

## Containers
Intercepte appels aux composants et ajoute
- transactions
- gestion de concurrence
- cycle de vie
- injection de dépendance

# Distribution de l'app
## Fichier d'archive
`.jar` contient
- `.class`
- ressources: `.png`, `.mp4`, etc...
- `.xml` deploy, describe...
    - `web.xml`
    - `payara-web.xml`
- `.jar`

### Types
- Jar (Java Archive): EJB, .class, ressources
- War (Web Archive): servlets, html, jsf, ejb...
- Ear (Entreprise Arhive)

# JSF
## Avantages
- Permet d'écrire simplement interface
- Intégré au reste du code Java

## Convient 
- si interface pas très complexe 
- si scalabilité faible

## Alternative
- SPA / Ajax
- Spring

# Cloud
...

# JNDI (Java Naming & Directory Interface)
Accéder à d'autres composants depuis un composant     
~ Alternative à l'injection de dépendance

```java
import javax.naming.InitialContext;

    try {
        InitialContext ic = new InitialContext(); 
        MonEJB monEJB = (MonEJB)
        ic.lookup("java:global/app/mod/MonEJB");
        ...
    }
```

# EJB

## Injecter
```java
@EJB
private MonEJB monEJB;
```

# Maven 
Décrire, construire, gérer dans un fichier `pom.xml`

## Commandes
- compile
- test
- package
- install
- deploy

## Fichiers
```
./
│
├──  src/
|    ├── main/
|    |   ├── java/ # sources .class
|    |   ├── resources/ # images, xml, config
|    |   └── webapp/ # html, jsf, web-inf
|    |
|    └── test/
└── target/
```

# Tests 
- Unitaire
- Intégration
- Fonctionnel