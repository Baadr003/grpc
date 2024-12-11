# Projet gRPC Spring Boot - Service Bancaire

Ce projet implémente un service bancaire utilisant Spring Boot et gRPC, offrant des fonctionnalités de gestion de comptes.

## Table des Matières

- [Technologies Utilisées](#technologies-utilisées)
- [Fonctionnalités](#fonctionnalités)
- [Structure du Projet](#structure-du-projet)
- [Définition du Service gRPC](#définition-du-service-grpc)
- [Configuration](#configuration)
- [Construction du Projet](#construction-du-projet)
- [Tests](#tests)
- [Dépendances](#dépendances)
- [Contribuer](#contribuer)
- [Licence](#licence)

## Technologies Utilisées

- Java 20
- Spring Boot 3.4.0
- gRPC 1.53.0
- Protocol Buffers 3.21.12
- Base de données H2 (en mémoire)
- Maven
- Spring Data JPA

## Fonctionnalités

- Gestion des comptes via des services gRPC
- Opérations CRUD pour les comptes bancaires
- Filtrage des comptes par type
- Calcul des soldes
- Stockage en mémoire avec la base de données H2

## Structure du Projet
grpc2/ ├── src/ │ ├── main/ │ │ ├── java/ │ │ │ └── ma/projet/grpc/ │ │ │ ├── Grpc2Application.java │ │ │ ├── controllers/ │ │ │ │ └── CompteServiceImpl.java │ │ │ ├── entities/ │ │ │ │ └── Compte.java │ │ │ ├── repositories/ │ │ │ │ └── CompteRepository.java │ │ │ ├── services/ │ │ │ │ └── CompteService.java │ │ │ └── stubs/ │ │ │ ├── CompteOuterClass.java │ │ │ ├── CompteRequest.java │ │ │ ├── DeleteCompteRequest.java │ │ │ ├── GetAllComptesRequest.java │ │ │ ├── GetComptesByTypeRequest.java │ │ │ ├── SaveCompteRequest.java │ │ │ └── ... │ │ └── resources/ │ │ ├── application.properties │ │ └── compte.proto │ └── test/ │ └── java/ │ └── ma/projet/grpc/ │ └── Grpc2ApplicationTests.java └── pom.xml

## Définition du Service gRPC

Le fichier `compte.proto` définit les services suivants :

```protobuf
service CompteService {
  rpc AllComptes(GetAllComptesRequest) returns (GetAllComptesResponse);
  rpc CompteById(GetCompteByIdRequest) returns (GetCompteByIdResponse);
  rpc TotalSolde(GetTotalSoldeRequest) returns (GetTotalSoldeResponse);
  rpc SaveCompte(SaveCompteRequest) returns (SaveCompteResponse);
  rpc ComptesByType(GetComptesByTypeRequest) returns (GetComptesByTypeResponse);
  rpc DeleteCompte(DeleteCompteRequest) returns (DeleteCompteResponse);
}

## Définition du Service gRPC

Le fichier `compte.proto` définit les services suivants :

```protobuf
service CompteService {
  rpc AllComptes(GetAllComptesRequest) returns (GetAllComptesResponse);
  rpc CompteById(GetCompteByIdRequest) returns (GetCompteByIdResponse);
  rpc TotalSolde(GetTotalSoldeRequest) returns (GetTotalSoldeResponse);
  rpc SaveCompte(SaveCompteRequest) returns (SaveCompteResponse);
  rpc ComptesByType(GetComptesByTypeRequest) returns (GetComptesByTypeResponse);
  rpc DeleteCompte(DeleteCompteRequest) returns (DeleteCompteResponse);
}
## Dépendances

-Spring Boot Starter Data JPA
-Spring Boot Starter Web
-Spring Boot DevTools
-H2 Database
-gRPC Spring Boot Starter
-Protocol Buffers
-Lombok
