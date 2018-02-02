## Gestion de projet : Comptes Utilisateurs API
### 1 - Introduction : 
##### 1-1 Descriptif
Ce projet est un service web (API) permettant la création, suppression, modification de comptes utilisateurs. Elle permet aussi une connexion/déconnexion d'un utilisateur.

##### 1-2 Auteurs

- HAMMY Mohammed El Habib
- **Email**: habib.hammy@gmail.com
- KABBOUCH Nasreddine
- **Email**: kabbouchnasreddine@gmail.com
### 2 - Mode d'utilisation :
#### 2-1 Prérequis:
Pour le bon fonctionnement de cette API, les programmes suivants sont nécessaires :

  * JRE 8 ou ultérieur
  * H2 database 1.4.196
  * Tomcat 8.5.14
   * IDE (Eclipse)
   * Maven 3.5.2
    
#### 2-2 Démarage:
Pour exécuter ce projet, suivez les instructions suivantes :

1. Dans Eclipse faite **{ [RightClick]>Maven>Update Porject }** puis **{ OK }** dans l'onglet qui s'ouvrira. Cela permettra d'importer toutes les dépendences du projet.

2. Puis faite **{ [RightClick]>Run As>Spring Boot App }** pour lancer le service.
 
### 3 - Descriptif Technique :
#### 3-1 Les routes :
Ce projet est un service web. il peut être requetté par d'autres applications via HTTP afin de remplir les fonctionnalités liées à la gestion des comptes utilisateurs. Il offre la possibilité de faire les requêtes suivantes :
 
 <span style="color:#193366">__1- [GET] "http://~/users/" :__</span>
    Cette route permet de récupérer l'ensemble des objets users 
    présent dans la base de données.
    Les users sont renvoyés sous format JSON :
    
```json
{
           "id": 100,
          "username": "alice",
          "email": "alice@exemple.com",
          "firstname": "alice",
          "lastname": "alice",
          "country": "FRANCE"
}
```
   
   <span style="color:#193366">__2- [GET] "http://~/users/{id}" :__</span>
   Cette route permet de récupérer L'objet user correspendant à l'id passé en paramétre.
   L'objet est renvoyé sous le même format JSON.
    
   <span style="color:#193366">__3- [POST] "http://~/users/add" :__</span>
     Cette route permet d'ajouter un utilisateur à la base de donnée en utilisant la méthode **POST**
     Elle prend en paramétre un username passé dans le header de la requête.
     
    
  <span style="color:#193366">__4- [PUT] "http://~/users/update":__</span>
    Cette route permet de modifier les informations un utilisateur dans la base de donnée en utilisant la méthode **PUT**
     Elle prend en paramétre un objet user sous format JSON dans le body de la requête.
     
   <span style="color:#193366">__5- [DELETE] "http://~/users/delete/{id}":__</span>
    Cette route permet de supprimer un utilisateur de la base de donnée en utilisant la méthode **DELETE**
     Elle prend l'id de l'utilisateur à supprimer comme paramétre dans l'URL de la requête.
     
   <span style="color:#193366">__6- [GET] "http://~/connexion/":__</span>
    Cette route permet de récupérer l'ensemble des correspendances des user-tokken générées.
     
   <span style="color:#193366">__7- [POST] "http://~/connexion/auth":__</span>
    Cette route permet à un utilisateur dans la base de donnée de s'identifier.
     Elle prend en paramétre un username et un mot de passe dans le header de la requête.
     Elle renvoie le tokken généré.
     
   <span style="color:#193366">__8- [POST] "http://~/connexion/isauth":__</span>
    Cette route permet le tokken d'un utilisateur. Cela permettra de vérifier si un utilisateur est bien authentifié.
    Elle prend en paramétre un username et son tokken passé dans le header de la requête.
    Elle renvoie ***'TRUE'*** ou ***'FALSE'*** .
     
   <span style="color:#193366">__9- [DELETE] "http://~/connexion/decon":__</span>
    Cette route permet à un utilisateur dans la base de donnée de ce déconnecter.
    Elle prend en paramétre un username et son tokken passé dans le header de la requête.
    Elle renvoie ***'TRUE'*** ou ***'FALSE'*** .
    
#### 3-2 Le model :

#### 3-3 Les services:

#### 3-4 La base de données:
