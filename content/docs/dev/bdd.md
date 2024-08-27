---
weight: 530
title: Base de donnés
description: Devloweb fonctionne en partie grâce à une base de donné. Regardons comment elle s'organise.
icon: database
draft: false
toc: true
---
## 👤 SELECT * FROM `users`
| ID         | Contexte                                                           |
| ---------- | ------------------------------------------------------------------ |
| `ja_id`    | Identifiant JA que l'utilisateur a utilisé lors de son inscription |
| `email`    | Email de l'utilisateur utilisé lors de son inscription             |
| `name`     | Nom de l'association, récupéré par l'api ZRNJA                     |
| `password` | Mot de passe crypté de l'utilisateur                               |
| `date`     | Date de création du compte                                         |
| `active`   | Statut du compte : 0 correspond à non validé et 1 validé           |
## ✅️ SELECT * FROM `verification`

| ID      | Contexte                      |
| ------- | ----------------------------- |
| `ja_id` | Identifiant de la JA          |
| `code`  | Code de vérification généré   |
| `date`  | Date de la génération du code |

## 🔐 SELECT * FROM `security`

| ID         | Contexte                                                       |
| ---------- | -------------------------------------------------------------- |
| `ip`       | Adresse ip de l'utilisateur qui échoue                         |
| `try`      | Nombre d'essaie fait par l'adresse IP.          *Par défaut 1* |
| `first`    | Date du pemière essaie échoué par l'adresse ip                 |
| `punition` | Date de la punition effectué                                   |

## 🌐 SELECT * FROM `sites`

| ID       | Contexte                                               |
| -------- | ------------------------------------------------------ |
| `ja_id`  | Identifiant de la JA                                   |
| `domain` | Domaine ou sous domaine sélectionné par la JA          |
| `theme`  | Thème sélectionné par la JA                            |
| `status` | Status du site. 0 correspond à en création, 1 à publié |

## 🪄 SELECT * FROM `magic_link`

| ID      | Contexte                               |
| ------- | -------------------------------------- |
| `code`  | Code du lien magique qui vérifie la JA |
| `ja_id` | Identifiant de la JA à vérifier        |
| `date`  | Date de création du code               |
