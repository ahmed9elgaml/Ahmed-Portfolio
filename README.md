# Ahmed Elgaml · Portfolio

My personal portfolio: who I am, what I've built, and the technical decisions behind it.

**Live:** https://ahmedelgaml.com

## What's in it

- **Home**: a short introduction, my projects, how I work, and how to reach me.
- **Project pages** (`/projects/:slug`): screenshots, the problem the project solves, and a
  technical deep dive (architecture, database, authentication, key decisions, lessons),
  with links to the real code for every claim.

## Stack

- React 19 + TypeScript, built with Vite
- Tailwind CSS v4 (design tokens in `frontend/src/index.css`)
- React Router 7
- No backend: a static site

## How it's organised

```
frontend/src/
  data/         all content (profile, projects, case studies): components only render it
  components/   pieces shared across the site (layout, ui)
  pages/        one folder per page; a piece used by one section lives inside that section
  hooks/        shared React hooks
  utils/        small plain functions
```

Content is data and presentation is components, so adding a project is mostly a new data file.

## Run it locally

```bash
cd frontend
npm install
npm run dev
```

Needs Node 20.19+ or 22.12+.

## Deploying

A static build (`npm run build` → `frontend/dist`). It's a single-page app, so the host must
serve `index.html` for every URL; `frontend/vercel.json` (Vercel) and
`frontend/public/_redirects` (Netlify, Cloudflare Pages) already set that up.
On the host, set the project's root directory to `frontend`.
