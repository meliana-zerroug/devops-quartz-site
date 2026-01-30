---
title: Lab 1
---

# Lab 1: 

## Description 

Ce lab est une première immersion dans le monde du DevOps. Il introduit le passage d'un programme exécuté localement puis via une application accessible sur internet grâce à un serveur. 
L'application utilisée est une application web développée en **Node.js**, qui a pour rôle d'afficher le message suivant : "Hello World".

Dans un premier temps, notre programme affiche le messaga attendu lorsque nous accédons à l'application via un navigateur. Pour cela, plusieurs actions sont réalisées.
Premièrement, nous allons créer l'arborescence du projet. Dans notre dossier **sample-app**, on crée notre fichier **app.js**. Cette application repose sur le module **http** de Node.js, qui permet de créer un serveur web capable de traiter des requêtes HTTP. 
À chaque requête reçue, le serveur renvoie une réponse avec un code HTTP 200 et le message 
« Hello World ».
Le serveur écoute sur le port par défaut "8080", ou un port défini grâce à la variable PORT.
Cela permet à l’application de s'adapter à différents environnements de déploiement.
Une fois déployé avec la commande **node app.js**, on peut ouvrir **http://localhost:8080** dans notre navigateur et voir le message **"Hello, World!"**.


## Objectifs
