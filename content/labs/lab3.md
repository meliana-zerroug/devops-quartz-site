---
title: Lab 3
---

# Lab 3: Déploiement et orchestration des applications

## Objectifs

- Comprendre les différentes méthodes de déploiement d’une application, du serveur classique au serverless.
- Déployer une application web sur plusieurs serveurs à l’aide d’**Ansible**.
- Mettre en place un **équilibrage de charge** et des **mises à jour progressives (rolling updates)**.
- Créer et déployer des images de machines virtuelles avec **Packer** et **OpenTofu**.
- Déployer une application conteneurisée avec **Docker** et **Kubernetes**.
- Mettre en œuvre des déploiements sans interruption de service.
- Comprendre le principe du **serverless** avec **AWS Lambda** et **API Gateway**.

## Description

Ce troisième lab a pour objectif de présenter différentes façons de déployer et gérer une application dans le cloud.
Il s’appuie sur une application web simple développée en **Node.js** et sur les services **AWS**.

### 1. Orchestration de serveurs avec Ansible

Dans un premier temps, le déploiement des applications est réalisé au niveau des **serveurs** à l’aide d’**Ansible**.  
Plusieurs instances **EC2** sont déployées automatiquement, puis configurées afin d’exécuter l’application **Node.js**.

Un **inventaire dynamique** est utilisé pour gérer les instances créées sur AWS.  
Un serveur **Nginx** est ensuite mis en place comme **load balancer**, permettant de répartir les requêtes entre plusieurs serveurs.  
Enfin, l’application est mise à jour progressivement afin de rester accessible pendant la mise à jour.

### 2. Orchestration de machines virtuelles avec Packer et OpenTofu

Le lab introduit ensuite le déploiement au niveau des **machines virtuelles**.  
Avec **Packer**, une image serveur contenant l’application et ses dépendances est créée. 
Cette image est ensuite utilisée par **OpenTofu** pour déployer automatiquement un groupe d’instances via **Auto Scaling Group**.

Un **Application Load Balancer (ALB)** est configuré pour exposer l’application et gérer le trafic.  
Les instances sont mises à jour une par une afin de garantir la disponibilité de l’application.

### 3. Orchestration de conteneurs avec Docker et Kubernetes

Dans cette partie, l’application est conteneurisée à l’aide de **Docker**.  
Une image Docker est construite puis exécutée localement afin de valider son fonctionnement.

L’application est ensuite déployée sur un cluster **Kubernetes**, d’abord en local, puis sur AWS à l’aide d’**EKS**.  
Ces concepts permettent de comprendre comment une application conteneurisée est déployée, rendue accessible et mise à jour.

### 4. Orchestration serverless avec AWS Lambda

Enfin, le lab introduit le concept de **serverless**, où aucune gestion de serveur n’est nécessaire.  
Une fonction **AWS Lambda** est créée et déployée à l’aide d’**OpenTofu**, puis rendue accessible depuis Internet grâce à **API Gateway**, 
afin de répondre à des requêtes **HTTP**. 
Cette approche met en avant les avantages du **serverless**, notamment la rapidité de mise en production et l’absence de gestion de l’infrastructure.
