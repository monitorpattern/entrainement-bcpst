# Entrainement BCPST

Application full-stack pour l'entraînement BCPST avec Vue 3 (frontend), FastAPI (backend) et PostgreSQL (database).

## Structure du projet

```
entrainement-bcpst/
├── frontend/       # Application Vue 3 + Vite
├── backend/        # API Python FastAPI
├── database/       # Scripts et migrations de base de données
└── docker-compose.yml
```

## Démarrage rapide

### Option 1: Avec Docker (recommandé)

```sh
docker-compose up -d
```

- Frontend: http://localhost:5173
- Backend API: http://localhost:8000
- Database: localhost:5432

### Option 2: Manuel

#### Frontend
```sh
cd frontend
npm install
npm run dev
```

#### Backend
```sh
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
uvicorn main:app --reload
```

#### Database
Installez PostgreSQL localement ou utilisez Docker:
```sh
docker run -d -p 5432:5432 -e POSTGRES_PASSWORD=password -e POSTGRES_DB=entrainement_bcpst postgres:16-alpine
```

---

## Frontend (Vue 3)

### Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Recommended Browser Setup

- Chromium-based browsers (Chrome, Edge, Brave, etc.):
  - [Vue.js devtools](https://chromewebstore.google.com/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)
  - [Turn on Custom Object Formatter in Chrome DevTools](http://bit.ly/object-formatters)
- Firefox:
  - [Vue.js devtools](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)
  - [Turn on Custom Object Formatter in Firefox DevTools](https://fxdx.dev/firefox-devtools-custom-object-formatters/)

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

### Commandes Frontend

```sh
cd frontend
npm install              # Installation des dépendances
npm run dev              # Développement
npm run build            # Build de production
npm run test:unit        # Tests unitaires
npm run lint             # Linting
```

## Backend (FastAPI)

Voir [backend/README.md](backend/README.md) pour plus de détails.

## Database (PostgreSQL)

Voir [database/README.md](database/README.md) pour plus de détails.
