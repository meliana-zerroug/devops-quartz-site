---
title: Home
publish: true
---

# **Bienvenue**

Cette page présente l’ensemble des réalisations effectuées dans le cadre des labs DevOps, mettant en œuvre les concepts clés d’automatisation, d’Infrastructure as Code et de déploiement cloud-native. Elle a pour but d’illustrer la construction progressive d’une infrastructure moderne, sécurisée et entièrement pilotée par le code.
# Architecture & Outils Utilisés
## Cloud Provider
# Amazon Web Services (AWS)
EC2


Security Groups


IAM


AMI


## Infrastructure as Code
Bash scripting (automatisation simple via AWS CLI)


Ansible: Configuration management & idempotence


Packer : Création d’AMI immuables


OpenTofu : Provisioning déclaratif




## Application déployée
Application Node.js simple


Déploiement automatisé sur EC2


Exposition via HTTP (port 80 / 8080)


# Pipeline DevOps Implémenté
Authentification sécurisée AWS (IAM + CLI)


Provisionnement automatique d’instances EC2


Création d’images personnalisées avec Packer


Déploiement via OpenTofu (avec modules réutilisables)


Mise à jour & destruction contrôlée des ressources


Gestion des changements via plan/apply


# Approche DevSecOps
Gestion des clés IAM


Infrastructure versionnée


Idempotence des configurations


Séparation modules / environnement live


Reproductibilité des environnements

