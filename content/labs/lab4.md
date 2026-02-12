---
title: Lab 4
---

# Lab 4 : Gestion du code, automatisation et tests

## Objectifs

- Utiliser **Git** pour gérer les versions d’un projet.
- Travailler de manière collaborative avec **GitHub**.
- Organiser un projet **Node.js** et automatiser des tâches avec **NPM**.
- Gérer les dépendances d’une application.
- Écrire et exécuter des **tests automatisés** pour une application.
- Vérifier le bon fonctionnement d’une infrastructure à l’aide de tests.

## Description

Ce quatrième lab a pour objectif d’introduire les pratiques fondamentales liées à la **gestion du code**, à l’**automatisation des tâches** et aux **tests**.
Il s’appuie sur une application web développée en **Node.js**.

### 1. Gestion des versions avec Git

Dans un premier temps, le lab aborde l’utilisation de **Git** pour gérer l’historique du code source.  
Les notions de dépôt, de commit et de branches sont mises en pratique afin de suivre les évolutions du projet et d’expérimenter différentes fonctionnalités sans impacter la version principale **main**.

### 2. Collaboration avec GitHub

Le lab introduit ensuite l'utilisation de **GitHub**.  
Le projet est publié sur un dépôt distant, permettant de travailler à plusieurs grâce aux branches et aux **pull requests**.  
Cette étape permet de comprendre comment le code est partagé, relu et validé lorsque l'on est plusieurs collaborateurs.

### 3. Automatisation avec NPM

Dans cette partie, **NPM** est utilisé pour automatiser certaines tâches du projet à l’aide de commandes dédiées.  
Les scripts définis dans le fichier **package.json** permettent d’exécuter des actions courantes sans avoir à taper des commandes longues ou complexes.

- **npm start** : cette commande permet de lancer l’application Node.js. Elle exécute le script associé dans **package.json**, ce qui démarre le serveur de l’application avec une seule commande.
- **npm run dockerize** : cette commande permet de construire automatiquement une image Docker de l’application. Elle appelle un script Bash qui se charge de la création de l’image, sans avoir besoin de lancer manuellement les commandes Docker.
- **npm test** : cette commande exécute l’ensemble des tests automatisés définis pour l’application. Elle permet de vérifier rapidement que le code fonctionne correctement avant un déploiement.

### 4. Tests automatisés de l’application

Dans ce lab on introduit ensuite les **tests automatisés** à l’aide de **Jest** et **SuperTest**.  
Des tests sont écrits afin de vérifier le bon fonctionnement des différentes routes HTTP de l’application.
Cette étape met en évidence l’intérêt des tests pour détecter rapidement les erreurs et garantir la stabilité du code.

### 5. Tests de l’infrastructure avec OpenTofu

Enfin, des tests sont appliqués au code d’infrastructure **OpenTofu**.  
Ces tests permettent de vérifier automatiquement qu’une infrastructure déployée répond aux attentes, comme la disponibilité d’un endpoint ou le contenu d’une réponse HTTP.
