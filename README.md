# Architecture Micro-services avec RestTemplate

## A - Mise en place du service discovery Eureka

**Contexte et utilité**

Le service discovery Eureka est un composant essentiel dans une architecture microservices. Il permet aux services de se découvrir mutuellement sans avoir à coder en dur les adresses IP et les ports. Cela facilite le déploiement, la mise à l'échelle et la résilience de l'application.

### Création d'un projet Spring Boot

<img width="924" height="503" alt="Capture d&#39;écran 2025-12-03 102524" src="https://github.com/user-attachments/assets/9c9b1771-ca53-4643-839a-d5f95d63ff35" />

### Exécution de l'application

<img width="922" height="503" alt="Capture d&#39;écran 2025-12-03 102618" src="https://github.com/user-attachments/assets/1fac40ed-f3b6-4a5e-a962-5e4bd93a0c78" />


---

## B - Microservice Client

Le microservice "Client" est une application Spring Boot qui gère les opérations associées à la gestion des clients. Ce service repose sur une base de données MySQL pour le stockage des informations essentielles des clients, telles que le nom et l'âge. Des points de terminaison RESTful sont exposés afin de permettre la récupération de la liste des clients, la recherche d'un client par identifiant, ainsi que l'ajout de nouveaux clients. L'intégration au service de découverte Eureka garantit la découverte automatique des services dans un environnement de type microservices.

### Configurer le service Spring Boot

<img width="925" height="499" alt="Capture d&#39;écran 2025-12-03 102938" src="https://github.com/user-attachments/assets/467e5367-a040-4ac8-8af3-1640344a5473" />

### Exécution de l'application

<img width="1920" height="1080" alt="Capture d’écran (1)" src="https://github.com/user-attachments/assets/0010d082-437b-4450-9ea7-4e5477bda53f" />

---

## C - Service Gateway

Le service "Gateway" assure la gestion centralisée des requêtes en utilisant Spring Cloud Gateway. Ce service permet la redirection des requêtes vers les microservices enregistrés dans le registre Eureka.

### Configurer le service Spring Boot

<img width="922" height="501" alt="Capture d&#39;écran 2025-12-03 104057" src="https://github.com/user-attachments/assets/37045719-8360-4f94-a964-9c8d0f3eb557" />

###  Exécuter l'application

<img width="914" height="496" alt="Capture d&#39;écran 2025-12-03 112400" src="https://github.com/user-attachments/assets/72120b63-e263-4319-877f-371adb5d5098" />

### Tester la découverte dynamique des routes

**http://localhost:8888/SERVICE-CLIENT/api/client.**

<img width="472" height="472" alt="Capture d&#39;écran 2025-12-03 114348" src="https://github.com/user-attachments/assets/7d6998cb-9acf-4449-893f-bc1bdd516a5d" />

<img width="923" height="414" alt="Capture d&#39;écran 2025-12-03 114404" src="https://github.com/user-attachments/assets/db72ebb2-b385-419c-a516-f488c39d0710" />

<img width="960" height="498" alt="Capture d&#39;écran 2025-12-03 125430" src="https://github.com/user-attachments/assets/86365bb0-5386-4baf-8a1a-6a4514d26242" />

<img width="924" height="426" alt="Capture d&#39;écran 2025-12-03 130202" src="https://github.com/user-attachments/assets/37d6cf30-c277-482a-b85e-b512e4939460" />

---

## D - Service Voiture

Le service "Voiture" assure la gestion des informations sur les voitures. Les principales opérations incluent la récupération de toutes les voitures, la recherche d'une voiture par identifiant et l'affichage des détails de la voiture ainsi que ceux du client associé.

### Création d'un projet Spring Boot

<img width="928" height="494" alt="Capture d&#39;écran 2025-12-03 131552" src="https://github.com/user-attachments/assets/9c62c9af-88ad-46ac-bcab-8028fc1272b4" />

### Lancement de l'application

<img width="926" height="487" alt="Capture d&#39;écran 2025-12-03 131647" src="https://github.com/user-attachments/assets/c7cf7e7e-8dd4-4fb0-81b0-83b2db21b99c" />

### Test des endpoints

**Base de donnees**

<img width="922" height="469" alt="Capture d&#39;écran 2025-12-03 130636" src="https://github.com/user-attachments/assets/577084a2-9dde-4b18-a742-5ca3830236b2" />

**GET http://localhost:8888/SERVICE-CAR/api/car**

<img width="960" height="499" alt="Capture d&#39;écran 2025-12-03 130723" src="https://github.com/user-attachments/assets/83b7eb25-96f3-4564-a35c-fa53f6956b3d" />

<img width="923" height="339" alt="Capture d&#39;écran 2025-12-03 131213" src="https://github.com/user-attachments/assets/6ebd2c16-23a6-4077-ab12-314d876114f5" />

**GET http://localhost:8082/api/car/1**

<img width="959" height="478" alt="Capture d&#39;écran 2025-12-03 131322" src="https://github.com/user-attachments/assets/9642acff-b373-4f9e-99a5-53e9734ab888" />

---

## Auteur

**Nom :** JARDI Siham

**Cours :** Architecture Microservices : Conception, Déploiement et Orchestration

**Date :** Decembre 2025

**Encadré par :** Pr.Mohamed LACHGHAR



