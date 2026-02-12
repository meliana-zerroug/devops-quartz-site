---
title: Lab 1
---

# Lab 1: 

## Objectifs

- Lancer localement une application
- Déployer une application automatiquement grâce à la plateforme PaaS
- Déployer  une application automatiquement grâce à l'infrastructure IaaS


## Description 

Ce lab constitue une première immersion dans le monde du **DevOps**.  
Il introduit le passage d’un programme exécuté localement à une application web accessible sur Internet grâce à un serveur.
L’application utilisée est une application web simple développée en **Node.js**, dont le rôle est d’afficher le message **"Hello World"** lorsqu’un utilisateur accède à l’application via un navigateur.

### 1. Exécution de l’application en local

Dans un premier temps, l’application est exécutée localement afin de vérifier son bon fonctionnement.  
Pour cela, l’arborescence du projet est créée et un fichier **app.js** est développé dans le dossier **sample-app**.

Cette application repose sur le module **http** de **Node.js**, qui permet de créer un serveur web capable de traiter des requêtes HTTP.  
À chaque requête reçue, le serveur renvoie une réponse avec un code HTTP 200 et le message **"Hello World!"**.
Le serveur écoute par défaut sur le port **8080**, ou sur un port défini à l’aide de la variable **PORT**. Cela permet à l’application de s’adapter à différents environnements de déploiement.
Une fois l’application lancée à l’aide de la commande **node app.js**, il est possible d’accéder à l’application via l’URL **http://localhost:8080**, où le message **"Hello World!"** s’affiche dans le navigateur.

### 2. Déploiement de l’application via une plateforme PaaS

Dans un second temps, l’application est déployée sur un serveur à l’aide d’une plateforme **PaaS (Platform as a Service)**.  
Cette méthode permet de déployer une application sans directement gérer l’infrastructure sous-jacente.
Ainsi, le code source de l’application est placé dans un dépôt **Git public**, qui est ensuite relié à la plateforme PaaS.  
La plateforme détecte automatiquement qu’il s’agit d’une application **Node.js**, installe les dépendances nécessaires et lance le serveur.
Une fois le déploiement terminé, une **URL publique** est générée. Cela permet à l'utilisateur d’accéder à l’application directement depuis un navigateur.

### 3. Déploiement de l’application via une infrastructure IaaS

Enfin, l’application est déployée à l’aide d’une infrastructure **IaaS (Infrastructure as a Service)**.  
Contrairement au **PaaS**, cette approche n’automatise pas le déploiement de l’application. Elle nécessite une configuration manuelle du serveur.
Une instance **EC2** est créée sur **AWS**, correspondant à un serveur virtuel distant.  
L’environnement est par la suite configuré manuellement, en particulier l’installation de **Node.js**, l’ouverture des ports réseau nécessaires et le lancement de l’application.

Afin d’automatiser le démarrage de l’application, un script de lancement appelé **user data** est utilisé.  
Grâce à ce script, l’application est automatiquement lancée au démarrage de l’instance et devient accessible via l’**adresse IP publique** du serveur.
