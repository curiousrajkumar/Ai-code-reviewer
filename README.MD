# AI Code Reviewer Pro

AI Code Reviewer Pro is a production-ready fullstack AI code reviewer and coding assistant with a premium React/Vite interface, JWT authentication, MongoDB persistence, Monaco Editor, animated dashboard, review history, settings, profile management, and AI-powered code analysis through Gemini or OpenAI.

## Tech Stack

- Frontend: React.js, Vite, React Router DOM, Framer Motion, Monaco Editor, Axios, CSS only
- Backend: Node.js, Express.js
- Database: MongoDB with Mongoose
- Auth: JWT and bcrypt password hashing
- AI: Gemini API or OpenAI API, with a local fallback analyzer when no API key is configured

## Project Structure

```text
frontend/
  src/components
  src/context
  src/layouts
  src/pages
  src/services
  src/styles
  src/utils
backend/
  src/config
  src/controllers
  src/middleware
  src/models
  src/routes
  src/services
  src/utils
```

## Local Setup

1. Install dependencies:

```bash
npm run install:all
```

2. Configure backend environment:

```bash
cp backend/.env.example backend/.env
```

Set `MONGODB_URI`, `JWT_SECRET`, and either `GEMINI_API_KEY` or `OPENAI_API_KEY`. The app still returns a local heuristic review if no AI key is present, which is useful for demos without paid API access.

3. Configure frontend environment:

```bash
cp frontend/.env.example frontend/.env
```

4. Run the backend:

```bash
npm run dev:backend
```

5. Run the frontend:

```bash
npm run dev:frontend
```

Open `http://localhost:5173`.

## API Overview

- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/me`
- `POST /api/ai/review`
- `POST /api/ai/optimize`
- `POST /api/ai/explain`
- `GET /api/history`
- `GET /api/history/:id`
- `DELETE /api/history/:id`
- `DELETE /api/history`
- `GET /api/user/profile`
- `PUT /api/user/profile`
- `GET /api/user/settings`
- `PUT /api/user/settings`

All AI, history, profile, and settings routes require a Bearer JWT.

## Deployment

### Frontend on Vercel

- Root directory: `frontend`
- Build command: `npm run build`
- Output directory: `dist`
- Environment variable: `VITE_API_URL=https://your-render-api.onrender.com/api`

### Backend on Render

- Root directory: `backend`
- Build command: `npm install`
- Start command: `npm start`
- Environment variables: `MONGODB_URI`, `JWT_SECRET`, `CLIENT_URL`, `AI_PROVIDER`, and your AI API key.

## Features

- Landing, login, register, dashboard, workspace, history, profile, pricing, settings, and 404 pages
- JWT authentication with persistent login and protected routes
- Monaco code editor and Monaco diff viewer
- Review, optimize, and explain AI actions
- Complexity, security, best practices, bug detection, suggestions, and optimized code output
- Copy, download, and print-to-PDF exports
- MongoDB review history and user settings
- Premium responsive UI with CSS-only styling and Framer Motion transitions
#