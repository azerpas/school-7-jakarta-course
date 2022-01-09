[← Home](../README.md)

## Combien de couches au moins dans une application Jakarta EE ?
- A. 1
- B. 2
- C. 3
- D. 4

<details>
  <summary>Answer</summary>
  3
</details>

## Jakarta EE
- A. Projet concurrent de Java EE
- B. Projet développé en interne par Oracle pour compléter Java EE
- C. Projet développé par plusieurs entreprises dont IBM, Oracle, Payara
- D. Projet open source
- E. C et D

<details>
  <summary>Answer</summary>
    E 
</details>

## Jakarta EE est
- A. un produit logiciel
- B. un ensemble de spécifications

<details>
  <summary>Answer</summary>
    B
</details>

## Une application Jakarta EE ne peut pas fonctionner sans
- A. JSF
- B. Un serveur d’application Jakarta EE
- C. Tomcat

<details>
  <summary>Answer</summary>
    B
</details>

## Dans quels cas il vaut mieux ne pas utiliser JSF pour l’interface utilisateur d’une application Jakarta EE ?
- A. Les utilisateurs de l’application sont très éloignés du serveur 
d’application
- B. On veut écrire une interface utilisateur très simple et très rapidement
- C. Les utilisateurs de l’application peuvent se connecter à l’application en très grand nombre en même temps

<details>
  <summary>Answer</summary>
    C
</details>

## Avantages des microservices
- A. Meilleure séparation entre les différentes parties d’une application
- B. Facilite la conception des applications
- C. Facilite la mise à jour d’une partie de l’application
- D. A et C
- E. Permet la distribution du code sur plusieurs ordinateurs,ce qui facilite l’écriture du code de l’application

<details>
  <summary>Answer</summary>
    D
</details>

## Il vaut souvent mieux commencer par écrire une application monolithe plutôt que d’écrire tout de suite des microservices
- A. Parce qu’il est difficile de partager une application en plusieurs microservices
- B. Pour se familiariser avec le domaine de l’application
- C. C’est faux, il est plus facile d’écrire directement des microservices car il faut moins de code pour écrire un microservice
- D. A et B

<details>
  <summary>Answer</summary>
    D
</details>

## MicroProfile est
- A. Un profile de Jakarta EE qui contient peu de fonctionnalités
- B. Un projet Eclipse pour les développement de microservices avec Java
- C. Permet d’utiliser un micro-ordinateur pour gérer une application Jakarta EE


<details>
  <summary>Answer</summary>
    B
</details>

## Ce qui caractérise une application cloud-native :
- A. utilise Internet pour la connexion des clients avec le serveur
- B. est déployée sur un serveur dans le cloud (on ne sait pas 
exactement où se trouve le serveur)
- C. peut s’adapter facilement aux pics de charge (des clients plus nombreux à certains moments)

<details>
  <summary>Answer</summary>
    B
</details>

## Avantages du cloud
- A. Coûts
- B. Flexibilité
- C. Sécurité

<details>
  <summary>Answer</summary>
    A B
</details>

## Dans quels cas le cloud peut ne pas être une bonne solution ?
- A. L’application contient de nombreux microservices
- B. L’application gère des données sensibles
- C. L’application a besoin de services avancés (par exemple la reconnaissance d’image)

<details>
  <summary>Answer</summary>
    B
</details>

## Un container Jakarta EE
- A. Sert à conserver des données dans une base de données
- B. Gère des composants Jakarta EE

<details>
  <summary>Answer</summary>
    B
</details>

## Un container EJB ne peut pas
- A. Démarrer une transaction
- B. Changer les valeurs des propriétés d’un EJB ou d’un bean CDI
- C. Créer un EJB

<details>
  <summary>Answer</summary>
    C
</details>

## Un container Docker est un des containers utilisés par un serveur d’application Jakarta EE
- A. Vrai
- B. Faux

<details>
  <summary>Answer</summary>
    A
</details>

## Qu’apporte l’utilisation des containers Docker ?
- A. Isolement des autres logiciels qui fonctionnent sur l’ordinateur hôte
- B. Indépendance par rapport à l’ordinateur hôte
- C. Utiliser le container pour intercepter les requêtes envoyées à l’application et offrir des services non fonctionnels (sécurité, transactions,...)
- D. A et B
- E. A, B et C

<details>
  <summary>Answer</summary>
    D
</details>

## L’application que vous développez peut avoir de très nombreux clients Web simultanés. Vous hésitez entre 2 architectures. Laquelle allez-vous choisir ?
- A. JSF pour l’interface utilisateur – EJB et JPA sur le serveur
- B. HTML5 et JavaScript pour l’interface utilisateur – Service Web REST (et souvent aussi EJB et JPA) pour le serveur

<details>
  <summary>Answer</summary>
    B
</details>

## Qu’est-ce que JAX-RS ?
- A. Une spécification Jakarta EE pour écrire des applications REST
- B. Une librairie Java pour faciliter les appels AJAX

<details>
  <summary>Answer</summary>
    A
</details>

## Spring est une des implémentations compatibles Jakarta EE
- A. Vrai
- B. Faux

<details>
  <summary>Answer</summary>
    B
</details>

## Qu’est-ce qu’une application « cloud-native » ?
- A. Une application dont l’interface utilisateur est constitué de pages Web
- B. Une application déployée sur Internet
- C. Une application qui utilise les services offerts par un fournisseur de cloud

<details>
  <summary>Answer</summary>
    C
</details>

## Que signifie « pay as you go » ?
- A. On paie l’utilisation d’une application ou d’un ordinateur le prix que l’on veut
- B. On paie l’utilisation d’une application ou d’un ordinateur selon ce que l’on fait avec
- C. On ne paie l’application ou l’ordinateur qu’une fois qu’on a fini de l’utiliser

<details>
  <summary>Answer</summary>
    B
</details>

## Avantages du cloud ?
- A. Peut adapter l’infrastructure aux pics d’utilisation
- B. Permet de changer facilement les ordinateurs qu’on a installé dans 
l’entreprise
- C. Facilite les tests des nouvelles applications
- D. Réduit les coûts

<details>
  <summary>Answer</summary>
    A, D
</details>

## Qu’est-ce qu’un microservice ?
- A. Logiciel faiblement couplé avec le reste de l’application, qui compose une application
- B. Un des services rendus par une application
- C. Un service qui rend très peu de services

<details>
  <summary>Answer</summary>
    A
</details>

##  Avantages des microservices ?
- A. Conception plus simple
- B. Mise à jour plus simple d’une partie de l’application
- C. Connexion plus simple entre les codes qui implémentent les services rendus par l’application
- D. Meilleure isolation des services
- E. L’application peut être écrite avec des langages différents pour chaque service

<details>
  <summary>Answer</summary>
    B, D, E
</details>

## Qu’est-ce qu’on appelle orchestration de containers ?
- A. Logiciel qui permet gérer les différents containers d’un serveur d’application
- B. Mécanisme qui permet de lancer automatiquement l’exécution de containers Docker à des moments fixés à l’avance
- C. Logiciel qui permet d’installer et de gérer tous les containers Docker qui composent une application

<details>
  <summary>Answer</summary>
    C
</details>

## Que signifie « Convention plutôt que configuration » ?
- A. Il ne faut pas configurer les applications
- B. Il ne faut jamais essayer des solutions non conventionnelles
- C. Il faut configurer seulement si les conventions ne conviennent pas

<details>
  <summary>Answer</summary>
    C
</details>

## Les applications Jakarta EE sont distribuées sous la forme de fichiers
- A. Zip
- B. Jar
- C. Tar
- D. Rar
- E. Gz

<details>
  <summary>Answer</summary>
    B
</details>

## S’il y a un conflit entre une configuration dans un fichier we- B.xml et avec 
une annotation, qui l’emporte ?
- A. we- B.xml
- B. L’annotation

<details>
  <summary>Answer</summary>
    A
</details>

## Un fichier ear peut contenir plusieurs fichiers jar ou war
- A. Vrai
- B. Faux

<details>
  <summary>Answer</summary>
    A
</details>

## Qu’est-ce qu’un profile Jakarta EE ?
- A. Un sous-ensemble de Jakarta EE
- B. Un outil pour écrire plus vite une application Jakarta EE

<details>
  <summary>Answer</summary>
    A
</details>

## EJB Lite est un
- A. EJB allégé en matière grasse
- B. Sous-ensemble des spécifications EJB
- C. Format qui permet de compacter un fichier qui contient des EJB

<details>
  <summary>Answer</summary>
    B
</details>

## JNDI sert à
- A. Enregistrer facilement des objets Java dans une base de données
- B. Retrouver des composants par leur nom
- C. Lancer des transactions

<details>
  <summary>Answer</summary>
    B
</details>

## Pour injecter des EJB dans une classe on est obligé d’utiliser JNDI
- A. Vrai
- B. Faux

<details>
  <summary>Answer</summary>
    B, @EJB
</details>

## Citez 3 types d’outils utiles pour développer une application Jakarta EE

<details>
  <summary>Answer</summary>
    IDE, Maven, Gradle, Git, JUnit, Terraform, Docker, ...
</details>

## Maven décrit un projet Jakarta EE en utilisant
- A. Java
- B. XML

<details>
  <summary>Answer</summary>
    B
</details>

## Un avantage de Maven est qu’il va automatiquement chercher les dépendances (les librairies utilisées par le projet) du projet, pendant l’exécution du projet
- A. Vrai
- B. Faux

<details>
  <summary>Answer</summary>
    B
</details>

## Un avantage de Maven est qu’il va automatiquement chercher les dépendances (les librairies utilisées par le projet) du projet
- A. Vrai
- B. Faux

<details>
  <summary>Answer</summary>
    A
</details>

## Maven gère automatiquement les dépendances transitives (les dépendances utilisées par les dépendances) du projet
- A. Vrai
- B. Faux

<details>
  <summary>Answer</summary>
    A
</details>

## Comment peut-on configurer Maven ?
- A. Avec we- B.xml
- B. Avec des annotations
- C. Avec pom.xml
- D. Avec des variables d’environnement

<details>
  <summary>Answer</summary>
    C
</details>