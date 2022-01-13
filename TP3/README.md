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

# Architecture des apps JSF
- Vue: **.jsf**     
↓
- Traitement UI: **Backing beans**    
↓
- Traitement BDD, services: **EJB**     
↓
- Intéraction BDD: **JPA, Entities**

## Template
```html
<!-- Page template -->
<ui:insert name="header">
```

```html
<!-- Use template -->
<ui:define name="header">...</ui:define>
```

## Convertisseur / Validateur standard
```html
<h:inputText id="dateNaissance" value="#{employe.dateNaissance}">
    <f:convertDateTime type="localDateTime" pattern="dd/MM/yyyy"/> <!-- convert to datetime -->
</h:inputText>
<h:message for="dateNaissance"/> <!-- convert error -->
```

## Convertisseur / Validateur non-standard
```java
// Classe annotée:
@FacesConverter
//// ou
@FacesValidator
```

### Code Java
```java
// Ex
public Converter<Discount> getDiscountConverter() {
    return new Converter<Discount>() {
        @Override public Discount getAsObject() { ... }

        @Override public String getAsString() { ... }
    }
}
```

### Code JSF
```js
<h:selectOneMenu 
    converter="#{clientDetailsBean.discountConverter}"
    id="discount" value="#{customerDetailsBean.client.discount}" 
> ...
</h:selectOneMenu>

```

### Validation d'un champ
```java
@Min(18) @Max(70)
private int age;
```

## Configuration
```html
<web-app>
    <context-param>
        <param-value>Development</param-value>
    </context-param>
    <session-config>
        <session-timeout>30</session-timeout>
    </session-config>
</web-app>
```

## Navigation
### POST
```jsx
<h:commandButton value="Voir liste"  action="liste.xhtml" />
```

### GET
```jsx
<h:link value="Voir les notes"  outcome="/notes/voirNotes" />
```

### Dynamique
```jsx
<h:commandButton action="#{bean.nav()}"/>
```
```java
@Named
@RequestScoped
public class Bean {
    public String nav(){
        if(a == 1) return "page2";
        else return "page1";
    }
}
```

### PRG (Post-Redirect-Get)
Éviter le rafraîchissement sur une page POST (double spending, etc...)