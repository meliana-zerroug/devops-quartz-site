---
title: Lab 5
---

# Lab 5 : Intégration Continue et Déploiement Continu (CI/CD)

## Objectifs

- Comprendre les principes de l’**intégration continue (CI)** et du **déploiement continu (CD)**.
- Mettre en place des **tests automatisés** pour une application et une infrastructure.
- Utiliser **GitHub Actions** pour automatiser des pipelines CI/CD.
- Authentifier GitHub Actions à **AWS** de manière sécurisée grâce à **OpenID Connect (OIDC)**.
- Automatiser le déploiement d’une infrastructure avec **OpenTofu**.

## Description

Ce cinquième lab a pour objectif de mettre en place une chaîne de **CI/CD** permettant d’automatiser les tests et le déploiement d’une application et de son infrastructure.  
Il s’appuie sur **GitHub Actions**, **AWS**, **OpenTofu** et **Kubernetes**, et prolonge les notions abordées dans les labs précédents.

### 1. Mise en place de l’intégration continue (CI)

Dans un premier temps, le lab introduit le principe de **l’intégration continue**, qui consiste à tester automatiquement le code à chaque modification.  
Un workflow **GitHub Actions** est configuré afin d’exécuter les tests de l’application **Node.js** à chaque *push* ou lors de la création d’une *pull request*.

Cette étape permet de vérifier que le code reste fonctionnel en permanence et de détecter rapidement les erreurs lors des modifications.

### 2. Tests automatisés de l’infrastructure

Le lab étend ensuite la CI aux **tests d’infrastructure**.  
Des tests **OpenTofu** sont exécutés automatiquement afin de vérifier que l’infrastructure déployée répond aux attentes, par exemple en testant l’accessibilité d’un endpoint HTTP ou le contenu d’une réponse.

Cette approche permet de vérifier à la fois le bon fonctionnement de l’application et celui de l’infrastructure qui l’héberge.

### 3. Authentification sécurisée avec OIDC

Afin d’éviter l’utilisation de clés AWS statiques, une authentification basée sur **OpenID Connect (OIDC)** est mise en place entre **GitHub Actions** et **AWS**.  
Des rôles **IAM** dédiés sont créés afin de permettre aux workflows d’accéder temporairement et de manière sécurisée aux ressources **AWS**.

Cette méthode améliore la sécurité et correspond aux bonnes pratiques DevOps.

### 4. Mise en place du déploiement continu (CD)

Dans cette partie, un pipeline de **déploiement continu** est configuré.  
Lorsqu’une *pull request* est ouverte, un workflow exécute la commande **tofu plan** afin de présenter les changements à venir.  
Une fois la *pull request* fusionnée sur la branche principale, un second workflow exécute **tofu apply**, ce qui déploie automatiquement l’infrastructure sur **AWS**.

Cette automatisation permet de rendre le déploiement sécurisé, reproductible et traçable.

