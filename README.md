# 🔧 Ochat API

**Backend** de l'application **Ochat**, une API RESTful développée en **Typescript** avec **Node.js** et **Express**

👉 [Voir la démo en ligne](https://ochat-front.vercel.app/)

👉 [Accèder au repo du frontend](https://github.com/SebastienCHAUVEL/ochat-front)

---

## 🎯 Objectifs du projet

Ce backend a été conçu pour :

1. **Fournir une API RESTful professionnelle**
2. **Gérer l'authentification sécurisée**
3. **Communiquer efficacement avec l'API Mistral**
4. **Assurer la persistance des données**

### 🔧 Particularités techniques

#### Approche POO avec les Models

- **Classes modèles bien structurées** :
  - Chaque entité (User, Conversation, Message) est représentée par une classe
  - Encapsulation des propriétés et méthodes
  - Typage fort

#### Pattern Data Mapper

- **Avantages de cette approche** :
  - Séparation claire entre **logique métier** et **accès aux données**
  - Meilleure **maintenabilité** du code
  - Possibilité de changer de système de stockage sans modifier la logique métier
  - Code plus propre et plus **organisé**

---

## 🛠 Technologies utilisées

### Core

- **Node.js**
- **Express**
- **PostgreSQL**

### Sécurité

- **CORS** (Gestion des requêtes cross-origin)
- **Helmet** (Sécurité des en-têtes HTTP)
- **express-xss-sanitizer** (Protection aux attaques XSS)

### Utilitaires

- **Zod** (Validation des entrées)
- **argon2** (Hashage des mots de passe)
- **jsonwebtoken** (Authentification)

---

## 🚀 Routes disponibles

### Authentification

  Méthode | Route          | Description                          | Authentification |
 |---------|----------------|--------------------------------------|------------------|
 | POST    | /auth/register | Inscription d'un nouvel utilisateur  | Non              |
 | POST    | /auth/login    | Connexion d'un utilisateur           | Non              |
 | PUT     | /auth/logout   | Déconnexion de l'utilisateur         | Oui              |
 | GET     | /users/me      | Récupérer les infos de l'utilisateur | Oui              |

### Conversations

  Méthode | Route                     | Description                              | Authentification |
 |---------|---------------------------|------------------------------------------|------------------|
 | GET     | /conversations            | Récupérer toutes les conversations       | Oui              |
 | POST    | /conversations            | Créer une nouvelle conversation          | Oui              |
 | PATCH   | /conversations/:id        | Mettre à jour une conversation           | Oui              |
 | DELETE  | /conversations/:id        | Supprimer une conversation               | Oui              |

### Messages

  Méthode | Route                                      | Description                                      | Authentification |
 |---------|--------------------------------------------|--------------------------------------------------|------------------|
 | GET     | /conversations/:conversationId/messages    | Récupérer tous les messages d'une conversation   | Oui              |
 | POST    | /conversations/:conversationId/messages    | Ajouter un message à une conversation            | Oui              |

### Mistral AI

  Méthode | Route          | Description                              | Authentification |
 |---------|----------------|------------------------------------------|------------------|
 | POST    | /prompt/mistral | Envoyer une requête à l'API Mistral      | Oui              |
