---
title: Lab 2
---

# Lab 2: 

## Objectifs

- Comprendre le principe d’Infrastructure as Code (IaC) et ses avantages par rapport à une gestion manuelle de l’infrastructure.
- Authentifier de manière sécurisée des outils DevOps afin d’interagir avec les services AWS.
- Automatiser le déploiement d’une instance EC2 à l’aide d’un script Bash.
- Déployer et configurer une instance distante à l'aide d'Ansible et de playbooks.
- Créer une image serveur (AMI) contenant une application préconfigurée à l’aide de Packer.
- Décrire, déployer, mettre à jour et supprimer une infrastructure cloud de manière déclarative avec OpenTofu.

## Description

Ce second lab permet de découvrir le principe d’**Infrastructure as Code (IaC)**.  
L’IaC consiste à déployer et gérer une infrastructure informatique à l’aide de scripts et de fichiers de configuration, plutôt que par des actions manuelles réalisées via une interface graphique. Voici des exemples de fichiers de configuration utilisés: des scripts **Bash**, des playbooks **Ansible** (.yml), des fichiers **Packer** (.pkr.hcl) et des fichiers **OpenTofu** (.tf).
L’infrastructure mise en place repose sur **AWS EC2** et une application web simple développée en **Node.js**.

### 1. Authentification et préparation de l’environnement AWS

Dans un premier temps, des **clés d’accès IAM** sont créées pour sécuriser au mieux les interactions avec **AWS**.  

### 2. Déploiement de l’infrastructure à l’aide d’un script Bash

L’infrastructure est ensuite déployée à l’aide d’un **script Bash**, permettant d’automatiser plusieurs actions :
- la création d’une instance **EC2**,
- la configuration du réseau,
- le lancement de l’application web.

Cette étape permet de comprendre les bases de l’automatisation de l’infrastructure, mais montre également les limites d’une approche basée uniquement sur des scripts.

### 3. Automatisation de la configuration avec Ansible

Ensuite, le lab introduit **Ansible**, qui permet d’automatiser la configuration des serveurs.  
Les ressources sont créées et configurées à l’aide de **playbooks**, qui définissent précisément l’état attendu du serveur.
Cette approche garantit une configuration idempotente, ce qui signifie que relancer un playbook ne modifie pas le serveur si celui-ci correspond déjà à l’état attendu.

### 4. Création d’une image serveur avec Packer

Le lab introduit ensuite **Packer**, utilisé pour créer une **AMI (Amazon Machine Image)**.  
Packer lance une instance EC2 temporaire, y installe **Node.js** ainsi que l’application, puis enregistre l’état complet du serveur afin de le transformer en AMI.

Cette image peut ensuite être réutilisée afin de déployer rapidement des serveurs déjà configurés, qui sont opérationnels dès leur démarrage.

### 5. Gestion déclarative de l’infrastructure avec OpenTofu

Enfin, **OpenTofu** est utilisé pour définir l’infrastructure cloud à l’aide de fichiers de configuration **.tf**.  
Ces fichiers décrivent les ressources attendues, telles que les instances EC2, les règles réseau ou les paramètres de démarrage.

OpenTofu se charge ensuite de créer, mettre à jour et supprimer les ressources nécessaires.  
Pour cela, on utilise les commandes suivantes :
- **tofu init** : prépare le projet,
- **tofu apply** : crée ou modifie les ressources,
- **tofu destroy** : supprime l’ensemble de l’infrastructure.
