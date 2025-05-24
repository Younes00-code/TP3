Ce projet consiste à développer une application Web de gestion des patients en utilisant les technologies Java EE (JEE), notamment Spring MVC, Thymeleaf pour le rendu côté client, Spring Data JPA pour la persistance des données, ainsi que Spring Security pour la gestion de l’authentification. L'application offre les fonctionnalités suivantes :

-Affichage de la liste des patients avec pagination
-Recherche de patients par mot-clé
-Suppression de patients
-Ajout et modification avec validation de formulaire
-Authentification via InMemory, JDBC, et UserDetailsService
-Utilisation d’un template réutilisable (layout)

*Technologies utilisées

-Java 21
-Spring Boot (starter web, data JPA, security, thymeleaf)
-Thymeleaf pour les vues
-Spring Data JPA avec H2/MySQL
-Spring Security pour l'authentification
-Bootstrap 5 pour le design responsive
![image](https://github.com/user-attachments/assets/631aa951-1162-49be-b5e3-0479ad9b6fe6)


*Fonctionnalités détaillées
 1 Affichage et pagination des patients
Utilisation de Page<Patient> avec Spring Data JPA
Contrôle de la page en cours, nombre de pages via l'URL (ex: /index?page=0)
Vue patients.html affiche une table avec les patients
![image](https://github.com/user-attachments/assets/bbf8def7-8984-4c4f-9f59-5249664e15de)


 2 Recherche des patients
Recherche par mot-clé (nom du patient)
URL : /index?keyword=Ahmed
Utilisation d'une méthode personnalisée dans PatientRepository

![image](https://github.com/user-attachments/assets/edcc3095-62dd-4e3e-ba45-80f4e74827b8)



 3 Suppression d’un patient
Lien de suppression dans le tableau
Requête GET vers /delete?id=1
Redirection vers la page principale après suppression

![image](https://github.com/user-attachments/assets/d3a6a266-faa9-413f-b458-b72a6faadac4)


  4 Formulaire avec validation
Vue formPatient.html avec formulaire de saisie
Annotations de validation : @NotEmpty, @Size, @Past, etc.
Utilisation de BindingResult pour afficher les erreurs
Ajout et modification d’un patient via le même formulaire

![image](https://github.com/user-attachments/assets/85f300ae-ca60-472e-bc0e-df5969ee3763)

![image](https://github.com/user-attachments/assets/64e98747-ad7c-4e82-a345-83aa051cf99e)

![image](https://github.com/user-attachments/assets/2a714cd8-1778-49db-a2c8-c60d9b590529)

*Authentification
1 InMemory Authentication
Configuration dans SecurityConfig.java 

![image](https://github.com/user-attachments/assets/9f6f5aab-b860-470c-a8a9-e17a145fa626)
2 JDBC Authentication
Base de données avec les tables users, authorities
Requêtes SQL personnalisées dans configure(AuthenticationManagerBuilder auth)

![image](https://github.com/user-attachments/assets/57242c9e-c09e-443d-a7e9-a1e480070d79)

*Sécurité et autorisations
Accès restreint aux fonctionnalités selon le rôle :
ROLE_USER : accès à la liste
ROLE_ADMIN : suppression et ajout autorisés
Formulaire de login personnalisé avec bootstrap
![image](https://github.com/user-attachments/assets/d16f358a-2e64-4a3c-b452-dbef84c018f9)

![image](https://github.com/user-attachments/assets/f050d1e1-508a-47e3-b43f-4b02a061a2aa)



![image](https://github.com/user-attachments/assets/9f10465e-b7c7-4df8-94fa-d1fbb84fcbfb)



