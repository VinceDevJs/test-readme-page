# 🪶 Twains

[![Deployed on Vercel](https://img.shields.io/badge/deploy-Vercel-000?logo=vercel&logoColor=white)](https://twains.vercel.app)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
![Version](https://img.shields.io/badge/version-0.1.0-yellow)
![Made with Next.js](https://img.shields.io/badge/Made%20with-Next.js-000?logo=nextdotjs)

Plateforme web moderne avec Next.js 15, Supabase, Prisma, TailwindCSS, et une interface pensée pour l’expérience utilisateur.

---

## 📚 Sommaire

- [🚀 Stack technique](#-stack-technique)
- [📁 Structure du projet](#-structure-du-projet)
- [📜 Scripts](#-scripts)
- [⚙️ Fichier `.env.local`](#️-fichier-envlocal)
- [🔐 Authentification](#-authentification)

---

## 🚀 Stack technique

| Technologie       | Usage                                      |
|------------------|---------------------------------------------|
| **Next.js 15**   | App Router + Server Actions (`use server`) |
| **React 19 RC**  | Composants client/serveur                   |
| **TypeScript**   | Typage fort                                 |
| **Supabase**     | Authentification & base de données postgres     |
| **Prisma**       | ORM                        |
| **Zod**          | Validation des schémas                      |
| **React Hook Form** | Formulaires avec validation intégrée   |
| **TailwindCSS**  | Style utilitaire                 |
| **Shadcn/UI**    | UI    |

---

## 📁 Structure du projet

```bash
src/
├── app/                  # Pages et routes via Next.js App Router
│   └── auth/             # Pages liées à l'authentification (sign-in, sign-up)
├── clients/              # Initialisation des clients Supabase et Prisma
├── components/           # Composants UI réutilisables
│   └── forms/            # Composants dédiés aux formulaires (SubmitButton, etc.)
├── hooks/                # Hooks personnalisés (useToast, useDebounce, etc.)
├── prisma/               # Schéma Prisma + types générés
```
---

## 📜 Scripts

| Commande         | Description                                 |
|------------------|---------------------------------------------|
| `pnpm dev`       | Démarre le serveur de développement         |
| `pnpm build`     | Build de l’app en production                |
| `pnpm start`     | Lance l’app après build                     |
| `pnpm lint`      | Lint + auto-fix                             |
| `pnpm tsc`       | Vérifie les types TypeScript                |
| `pnpm migrate`   | Migration Prisma via `.env.local`           |
| `pnpm generate`  | Génère les types Prisma                     |
| `pnpm prepare`   | Active Husky pour les hooks Git             |

---

## ⚙️ Fichier `.env.local`

Créer un fichier `.env.local` à la racine :

```env
# Environment setting
NODE_ENV="development"  # Change to "production" or "test" as needed

# Prisma database URL
DATABASE_URL=""
DIRECT_URL=""

# Supabase credentials
NEXT_PUBLIC_SUPABASE_URL=""
NEXT_PUBLIC_SUPABASE_ANON_KEY=""

# Resend API key
RESEND_API_KEY=""

# Base de l'URL utilisée pour construire des liens de redirections
NEXT_PUBLIC_APP_URL=""

# Permet d'avoir les droits admin notamment pour générer des link supabase
SUPABASE_SERVICE_ROLE_KEY=""

# Mollie API key
MOLLIE_API_KEY=""

```

## 🔐 Authentification

Présentation du système d’authentification mis en place avec **Supabase Auth** :

🎥 [Voir la démonstration Loom](https://www.loom.com/share/b8927fffcbf04eae9fbc96b87ecf6ae3?sid=7777ef40-caff-41aa-9ff6-47719aea6679)

> 📌 À noter : une vérification supplémentaire a été ajoutée après l’enregistrement de la vidéo.  
> Le système prend désormais en charge les redirections personnalisées via un paramètre `redirectUrl`, tout en s’assurant que l’URL cible figure bien parmi les destinations autorisées.  
> Cela renforce la sécurité en bloquant toute tentative de redirection vers un domaine externe.
