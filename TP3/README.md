[← Home](../README.md)    
[→ TP3](https://github.com/azerpas/school-7-jakarta)

# CM3

# JSF
Vue pour dev Web
- Facelets, langage (XHTML) pour des .jsf 
- Enregistré sur serveur, transmis en HTML

## EL, lien avec Backing Bean
Expression Language, rpz données dynamiques lié à Backing Bean
```jsx
#{utilisateur.hello()}
```

### Exemple
#### JSF - index.xhtml
```jsx
// ...
<h:form>
    <h3> Présentation </h3>
    Nom: <h:inputText value="#{utilisateur.nom}"/>
    <h:commandButton value="Save" action="#{utilisateur.hi()}"/> 
</h:form>
// ...
```

#### Backing Bean - Utilisateur
```java
@Named
@RequestScoped
public class Utilisateur {
    private String nom;
    // ...
    public String hi(){
        return "hello-world"; // page à afficher
    }
}
```

## Avantages JSF
- input vers serveur
- validation données
- alert automatisées
- internationalisation
- ajax sans prog
- librairies