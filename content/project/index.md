---
title: Projet : End-to-End Kubernetes DevSecOps
publish: true
---

# Objectif

Ce projet met en place une chaîne **DevSecOps complète** pour déployer une application **Tetris** sur **AWS EKS**.

L’idée est de couvrir tout le cycle :

- provisionnement d’infrastructure avec **Terraform**,
- intégration continue avec **Jenkins**,
- contrôle qualité et sécurité,
- build d’images Docker,
- déploiement Kubernetes sur EKS.


# Description

## Structure du projet et rôle de chaque dossier

### `EKS-TF/`

Contient l’Infrastructure as Code Terraform pour AWS EKS :

- VPC et réseau,
- cluster EKS,
- node groups,
- rôles/politiques IAM,
- variables et backend d’état Terraform.

## Flux technique global

1. Terraform crée l’infrastructure AWS (Jenkins, EKS, IAM, VPC).
2. Jenkins exécute les pipelines CI/CD.
3. Le code est analysé (qualité/sécurité), puis conteneurisé.
4. L’image est déployée sur Kubernetes (EKS) via manifests.
5. L’application Tetris est exposée via Service/Ingress.

## Outils DevSecOps utilisés

- **Terraform** : provisioning infrastructure.
- **Jenkins** : orchestration CI/CD.
- **Docker** : conteneurisation applicative.
- **Kubernetes (EKS)** : orchestration de déploiement.
- **SonarQube / Trivy / Dependency-Check** (selon pipeline) : qualité et sécurité.

## Résultat attendu

Le projet montre une implémentation pratique d’une chaîne DevSecOps cloud-native :

- reproductible,
- automatisée,
- orientée sécurité,
- déployée sur AWS EKS.

## Risques techniques identifiés

Les principaux risques observables dans ce type d’architecture sont :

- **Mauvaise configuration IAM** pouvant exposer des permissions excessives.
- **Dépendance à des secrets mal gérés** (variables Jenkins, tokens, clés cloud).
- **Dérive d’infrastructure** si les changements manuels ne sont pas reconsolidés via Terraform.
- **Vulnérabilités images Docker** si la base image et les paquets ne sont pas mis à jour.
- **Point de défaillance Jenkins** en cas d’instance unique non hautement disponible.

## Limites actuelles du projet

Dans sa forme actuelle, le projet se concentre surtout sur l’automatisation de bout en bout. Les limites possibles sont :

- observabilité partielle (metrics, logs centralisés, tracing non détaillés),
- gouvernance sécurité dépendante de la rigueur pipeline,
- stratégie de rollback non explicitée dans la documentation,
- absence d’indicateurs chiffrés consolidés dans un tableau de bord unique.

## Améliorations recommandées

- Ajouter des **quality gates bloquantes** (qualité + sécurité) avant déploiement.
- Versionner et automatiser la gestion des secrets (KMS/Secret Manager/External Secrets).
- Standardiser les stratégies de tags d’images et de promotion d’environnements.


## Conclusion 

Ce projet constitue une base solide pour démontrer la mise en œuvre d’un pipeline DevSecOps cloud-native sur AWS. Il couvre les briques essentielles (IaC, CI/CD, conteneurisation, orchestration Kubernetes) et offre un cadre réaliste pour mesurer la performance opérationnelle, renforcer la posture sécurité et améliorer la fiabilité globale du cycle de livraison logiciel.



