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

# Profiles
## Profile
Permet à des app d'utiliser une partie des tech de la norme