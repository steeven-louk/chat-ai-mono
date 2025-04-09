# 🧠 ChatIA - Monorepo Fullstack
Ce projet est une application de chat fullstack avec authentification via Clerk, stockage de médias via ImageKit, et persistance des données via MongoDB.
Le projet est structuré sous forme de monorepo avec un dossier client (frontend) et un dossier backend.


chatia-monorepo/
├── client/           # Frontend React avec React Router
├── backend/          # Backend Express + Clerk + MongoDB + ImageKit
├── .env              # Variables d’environnement partagées
├── .gitignore
└── README.md         # Ce fichier

## 🚀 Installation
1. Cloner le dépôt:
```
    git clone https://github.com/ton-utilisateur/chatia-monorepo.git
    cd chatia-monorepo

```

## 📦 Backend (Express)
📁 Accès au dossier backend
```
cd backend
git clone https://github.com/steeven-louk/chat_ai_backend.git
```

### 🔧 Variables d’environnement (backend/.env)

```
MONGO="mongodb+srv://<user>:<password>@goals.5ledc.mongodb.net/chat_gpt?retryWrites=true&w=majority"

IMAGE_KIT_ENDPOINT="https://ik.imagekit.io/<ton_id>"
IMAGE_KIT_PUBLIC_KEY="<ta_cle_publique>"
IMAGE_KIT_PRIVATE_KEY="<ta_cle_privee>"

CLIENT_URL="http://localhost:5173"
port=5000

CLERK_SECRET_KEY="<ta_cle_secret_key>"
CLERK_PUBLISHABLE_KEY="<publishable_key>"

```

### Lancer le server(backend)
```
npm install
npm start || nodemon
```
Le backend démarre sur http://localhost:5000

## 🌐 Frontend (React)
📁 Accès au dossier frontend

```
cd client
git clone https://github.com/steeven-louk/chat-ai-mono.git
```

### 🔧 Variables d’environnement (client/.env)

```
VITE_API_URL="http://localhost:5000"
VITE_IMAGE_KIT_ENDPOINT="<endpoint_key>"
VITE_IMAGE_KIT_PUBLIC_KEY="<public_key>"
VITE_GEMINI_PUBLIC_KEY="<ta_secret_key_gemini>"
VITE_CLERK_PUBLISHABLE_KEY="<ta_cle_publishable>"
VITE_CLERK_SECRET_KEY="<ta_secret_key>"
```

### Lancer le frontend
```
npm i --legacy-peer-deps
npm run dev
```
L’application démarre sur http://localhost:5173

## 🔐 Authentification Clerk
- Clerk est utilisé pour gérer l'authentification et la protection des routes côté backend via ClerkExpressRequireAuth().

- Sur le frontend, ClerkProvider est intégré avec React Router.

## 🧪 Fonctionnalités
- ✅ Authentification sécurisée via Clerk

- 🧠 Création et gestion de conversations (chats)

- 🖼️ Upload d’images avec ImageKit

- 🗃️ Sauvegarde des conversations MongoDB (Chat + UserChats)

- 🧭 Routing dynamique pour les pages de chat (/dashboard/chats/:id)

## 🐞 Débogage

- En local : vérifier que .env est bien renseigné.

- En prod (Railway, Vercel, etc.) : penser à configurer les variables d’environnement.

- Pour les erreurs Unauthenticated, assure-toi que :

-- La clé CLERK_SECRET_KEY côté backend est valide

-- Le domaine frontend est autorisé dans le dashboard Clerk

## 🛰️ Déploiement
✅ Railway (backend)
Déclare les variables d’environnement dans les paramètres Railway

Configure le domaine dans Clerk (ex : https://chataibackend.up.railway.app)

✅ Vercel (frontend)
Déclare VITE_BACKEND_URL et VITE_CLERK_PUBLISHABLE_KEY

Assure-toi que le domaine Vercel est ajouté dans Clerk