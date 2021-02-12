# SAMPLE GET STARTED


Project prerequisite versions :
* JDK >= 1.8
* Maven >= 3.6.3

## 1) Database configuration
*Vous pouvez passer cette étape si vous ne souhaitez pas utiliser l'application immédiatement mais elle nécessite cette base de données pour la persistance d'informations*

Pour ce projet vous aurez besoin d'une base de données [MySQL](https://dev.mysql.com/downloads/installer/), [MariaDb](https://mariadb.org/download/) ou équivalent.

Éditez le fichier situé dans `src/main/ressource/application.properties` avec les détails de connection de votre base de données en faisant un copié-collé du template de configuration ci-dessous. (Créez le fichier `application.properties` s’il n'existe pas)

la ligne `spring.datasource.url` contient toutes les information pour gérer une connexion avec une base MySql standard, en cas de modification de la base données (ex : Postgres) préférez alors vous référer à la doc Spring-Boot JPA pour effectuer cette transition.

```
################### DataSource Configuration ##########################
spring.datasource.url=jdbc:mysql://<adress>:<port>/<db>?useUnicode=true&useJDBCCompliantTimezoneShift=true&useLegacyDatetimeCode=false&serverTimezone=UTC
spring.datasource.username=<username>
spring.datasource.password=<password>
spring.datasource.driverClassName=com.mysql.cj.jdbc.Driver

################### JPA Configuration ##########################
spring.jpa.database-platform=org.hibernate.dialect.MySQL57Dialect
spring.jpa.generate-ddl=true
spring.jpa.hibernate.ddl-auto=create
```

Remplacez les valeurs `<adress>`, `<port>`, `<db>`, `<username>` et `<password>` respectivement pas l'adresse de la base de données (`localhost` dans la majorité des cas), le port de la base de données (`3306` par défaut), le nom de la database attribuée, le nom d'utilisateur pour se connecter et le mot de passe de connexion pour cet utilisateur.

Une fois ces changements effectués vous pouvez sauvegarder et fermer le fichier.

## 2) Java & Maven

Pour lancer ce projet vous aurez besoin de configurer votre JDK et votre Maven. Ici le projet est configuré pour fonctionner à partir de Java 8.

### Java SDK

Assurez-vous de posséder une version de Java (JVM) installée sur votre machine, si ce n'est pas le cas vous pouvez vous la [procurer ici](https://www.java.com/fr/download/).

Télécharger le SDK correspondant en vous rendant sur [cette page](https://www.oracle.com/fr/java/technologies/javase-downloads.html) puis installez le. Une fois installé le chemin devrais ressembler a `C:\Program Files\Java\jdk-X` où `X` correspond à la version de votre JDK

### Maven Binary

Téléchargez en suite les `Binary zip package` sur la page de téléchargement de Maven [en vous rendant ici](https://maven.apache.org/download.cgi).
Une fois téléchargé, ouvrez l'archive ZIP et extrayez le fichier nommé `apache-maven-X` où `X` correspond à la version actuelle de Maven dans un dossier.

⚠ **ATTENTION VOUS NE DEVREZ PAS CHANGER D'EMPLACEMENT LE FICHIER DE MAVEN UNE FOIS MIS EN PLACE** ⚠

### Path variable

Ouvrez le gestionnaire de variables d'environnement, pour cela vous avez deux possibilités :

* Dans la barre de recherche windows tapez `env` ou `environnement` et ouvrez `Modifiez les variables d'environnement pour votre compte
* Rendez-vous dans le panneau de configuration -> Système et sécurité -> Système -> Paramètres système avancés -> Variables d'environnement...

Une fois ce panneau ouvert cliquez sur le bouton `Nouvelle` du panneau supérieur puis rentrez ces deux valeurs :

* Nom de la variable : `JAVA_HOME`
* Valeur de la variable : `[Remplacez ici par le chemin d'accès de votre JDK précédement installé (ex : C:\Program Files\Java\jdk-15.0.2)]`

Une fois les deux valeurs rentrée vous pouvez cliquer sur `OK` et créer une `Nouvelle` variable à nouveau rentrez les deux valeurs :
* Nom de la variable : `MAVEN_HOME`
* Valeur de la variable : `[Remplacez ici par le chemin d'accès de votre dossier Maven précédement extrait (ex : C:\Program Files\apache-maven-3.6.3)]`

Une fois modifié cliquez sur `OK` et trouver dans la liste des Variables utilisateurs la variable nommée `Path`, cliquez dessus et cliquez en suite sur modifier. Une fois dans le nouveau panneau ouvert cliquez sur `Nouveau` puis ajoutez la même valeur que pour le dossier maven mais en ajoutant cette fois-çi `\bin` à la fin du chemin (ex : `C:\Program Files\apache-maven-3.6.3\bin`).
Puis vous pouvez valider vos changements et quitter ce panneau.

## Download and Run

Une fois le projet [téléchargé](http://git.uha4point0.fr/UHA40/fnesi/fnesi-back.git) ouvrez un terminal en vous rendant dans le dossier du projet et enfin lancez la commande  `mvn spring-boot:run`

Le projet devrais maintenant démarrer et en vous rendant sur l'adresse : [http://localhost:8080/](http://localhost:8080/) le message `Fnesi app Running` devrait s'afficher.

**Félicitation !** Le projet tourne maintenant sur votre machine !
